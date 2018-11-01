---
title: 'Gewusst wie: Marshallen eingebetteter Zeiger mit PInvoke'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
ms.openlocfilehash: 4f2d37ceb18035747773d307885c8af17d696adc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452077"
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>Gewusst wie: Marshallen eingebetteter Zeiger mit PInvoke

Funktionen, die in nicht verwaltete DLLs implementiert sind, können in verwaltetem Code mithilfe von Plattformaufruf (P/Invoke) Funktionen aufgerufen werden. Wenn der Quellcode für die DLL nicht verfügbar ist, ist P/Invoke die einzige Option für die Interoperation. Im Gegensatz zu anderen .NET-Sprachen bietet Visual C++ jedoch eine Alternative zum P/Invoke. Weitere Informationen finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) und [Vorgehensweise: Marshallen eingebetteter Zeiger mithilfe C++ Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).

## <a name="example"></a>Beispiel

Übergeben von Strukturen zu systemeigenem Code erfordert, dass eine verwaltete Struktur, die im Hinblick auf Layout für die systemeigene Struktur entspricht erstellt wird. Strukturen, die Zeiger enthalten erfordern jedoch besondere Behandlung. Für jede eingebettete Zeiger in die systemeigene Struktur ist, sollte die verwaltete Version der Struktur eine Instanz von enthalten die <xref:System.IntPtr> Typ. Darüber hinaus Arbeitsspeicher für diese Instanzen explizit zugeordnet werden müssen, initialisiert und veröffentlicht, mit der <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>, und <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> Methoden.

Der folgende Code besteht aus einer nicht verwalteten und ein verwaltetes Modul. Das nicht verwaltete Modul handelt es sich um eine DLL, die eine Funktion, die eine Struktur namens ListString, die einen Zeiger enthält, akzeptiert, und eine Funktion namens TakesListStruct definiert. Das verwaltete Modul ist eine befehlszeilenanwendung, die die Funktion TakesListStruct importiert und definiert eine Struktur namens MListStruct, die die native ListStruct entspricht, außer dass Sie mit der doppelten * dargestellt wird ein <xref:System.IntPtr> Instanz. Vor dem Aufruf TakesListStruct an, die main-Funktion weist und initialisiert den Speicher, den dieses Feld verweist.

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

Beachten Sie, dass kein Teil der DLL verfügbar gemacht wird, auf den verwalteten Code mithilfe der herkömmlichen #include-Anweisung. Tatsächlich ist die DLL zur Laufzeit nur zugegriffen, damit Probleme mit Funktionen mit importiert <xref:System.Runtime.InteropServices.DllImportAttribute> zum Zeitpunkt der Kompilierung nicht erkannt.

## <a name="see-also"></a>Siehe auch

[Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)