---
title: 'Wie: Marshallen eingebetteter Zeiger mit PInvoke | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a07c9742c393abe2a6213378ee8963839ab66c90
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>Gewusst wie: Marshallen eingebetteter Zeiger mit PInvoke
Funktionen, die in nicht verwaltete DLLs implementiert werden, können in verwaltetem Code mithilfe des Plattformaufrufs (P/Invoke) aufgerufen werden. Wenn der Quellcode für die DLL nicht verfügbar ist, ist P/Invoke die einzige Option für die Interoperation. Im Gegensatz zu anderen bietet Visual C++ jedoch eine Alternative zum P/Invoke. Weitere Informationen finden Sie unter [mithilfe von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) und [wie: Marshallen eingebetteter Zeiger mithilfe von C++-Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
## <a name="example"></a>Beispiel  
 Übergeben von Strukturen zu nativem Code erfordert, dass eine verwaltete Struktur, die im Hinblick auf Datenlayout der systemeigenen Struktur entspricht erstellt wird. Strukturen, die Zeiger enthalten sind jedoch besondere Behandlung erfordern. Für jede eingebettete Zeiger in die systemeigene Struktur ist, sollte die verwaltete Version der Struktur eine Instanz von enthalten die <xref:System.IntPtr> Typ. Darüber hinaus Arbeitsspeicher für diese Instanzen explizit zugewiesen werden müssen, initialisiert usw., freigegeben mit der <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>, und <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> Methoden.  
  
 Der folgende Code besteht aus einem nicht verwalteten und ein verwaltetes Modul. Nicht verwaltete Modul ist eine DLL, die eine Funktion, die eine Struktur, die Namen, die einen Zeiger enthält ListString akzeptiert, und eine Funktion namens TakesListStruct definiert. Verwaltete Modul ist eine befehlszeilenanwendung, die die Funktion TakesListStruct importiert und definiert eine Struktur mit dem Namen MListStruct, die der systemeigene ListStruct entspricht, außer dass mit Double * dargestellt wird ein <xref:System.IntPtr> Instanz. Vor dem Aufrufen von TakesListStruct, die Hauptfunktion reserviert und initialisiert den Speicher, den dieses Feld verweist.  
  
```cpp  
// TraditionalDll6.cpp  
// compile with: /EHsc /LD  
#include <stdio.h>  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct ListStruct {  
   int count;  
   double* item;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API void TakesListStruct(ListStruct);  
}  
  
void TakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
```  
  
```cpp  
// EmbeddedPointerMarshalling.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MListStruct {  
   int count;  
   IntPtr item;  
};  
  
value struct TraditionalDLL {  
    [DllImport("TraditionalDLL6.dll")]  
   static public void TakesListStruct(MListStruct);  
};  
  
int main() {  
   array<double>^ parray = gcnew array<double>(10);  
   Console::WriteLine("[managed] count = {0}", parray->Length);  
  
   Random^ r = gcnew Random();  
   for (int i=0; i<parray->Length; i++) {  
      parray[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);  
   }  
  
   int size = Marshal::SizeOf(double::typeid);  
   MListStruct list;  
   list.count = parray->Length;  
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);  
  
   for (int i=0; i<parray->Length; i++) {  
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);  
      Marshal::StructureToPtr(parray[i], t, false);  
   }  
  
   TraditionalDLL::TakesListStruct( list );  
   Marshal::FreeCoTaskMem(list.item);  
}  
```  
  
 Beachten Sie, dass kein Teil der DLL bereitgestellt wird, auf den verwalteten Code, der mithilfe der herkömmlichen #include-Direktive. Tatsächlich wird die DLL zur Laufzeit nur zugegriffen, damit Probleme mit Funktionen mit importiert <xref:System.Runtime.InteropServices.DllImportAttribute> zum Zeitpunkt der Kompilierung nicht erkannt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)