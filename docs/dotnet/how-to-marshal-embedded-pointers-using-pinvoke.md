---
title: "Gewusst wie: Marshallen eingebetteter Zeiger mit PInvoke"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenmarshalling [C++], Eingebettete Zeiger"
  - "Eingebettete Zeiger [C++]"
  - "Interop [C++], Eingebettete Zeiger"
  - "Marshaling [C++], Eingebettete Zeiger"
  - "Plattformaufruf [C++], Eingebettete Zeiger"
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen eingebetteter Zeiger mit PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Funktionen, die in nicht verwalteten DLLs implementiert sind, können von verwaltetem Code über Plattformaufrufe \(P\/Invoke\) aufgerufen werden.  Wenn der Quellcode für die DLL nicht verfügbar ist, ist P\/Invoke die einzige Option für die Interoperation.  Im Gegensatz zu anderen .NET\-Sprachen stellt Visual C\+\+ jedoch eine Alternative zu P\/Invoke bereit.  Weitere Informationen finden Sie unter [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md) und [Gewusst wie: Marshallen von eingebetteten Zeigern mit C\+\+\-Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
## Beispiel  
 Das Übergeben von Strukturen an systemeigenen Code setzt voraus, dass eine im Datenlayout der systemeigenen Struktur äquivalente verwaltete Struktur erstellt wird.  Strukturen, die Zeiger enthalten, erfordern dabei eine besondere Behandlung.  Für jeden eingebetteten Zeiger der systemeigenen Struktur sollte die verwaltete Version der Struktur eine Instanz des <xref:System.IntPtr>\-Typs enthalten.  Außerdem muss der Speicher für diese Instanzen mit den Methoden <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem*>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr*> und <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem*> explizit belegt, initialisiert und freigegeben werden.  
  
 Der folgende Code besteht aus einem nicht verwalteten und einem verwalteten Modul.  Das nicht verwaltete Modul ist eine DLL, die eine Funktion definiert und eine Struktur mit dem Namen ListString akzeptiert, die einen Zeiger und eine Funktion mit dem Namen TakesListStruct enthält.  Das verwaltete Modul ist eine Befehlszeilenanwendung, die die TakesListStruct\-Funktion importiert und eine Struktur mit dem Namen MListStruct definiert, die der systemeigenen ListStruct\-Struktur entspricht, mit der Ausnahme, dass der double\* durch eine <xref:System.IntPtr>\-Instanz dargestellt wird.  Vor dem Aufrufen von TakesListStruct belegt die Hauptfunktion den Speicher, auf den dieses Feld verweist, und initialisiert diesen.  
  
 Das verwaltete Modul wird mit \/clr kompiliert, es kann jedoch auch \/clr:pure verwendet werden.  
  
```  
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
  
```  
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
  
 Beachten Sie, dass mithilfe der herkömmlichen \#include\-Direktive kein Teil der DLL für den verwalteten Code verfügbar gemacht wird.  Tatsächlich wird auf die DLL nur bei der Ausführung zugegriffen, sodass Probleme mit Funktionen, die mit <xref:System.Runtime.InteropServices.DllImportAttribute> importiert wurden, zur Kompilierungszeit nicht erkannt werden.  
  
## Siehe auch  
 [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)