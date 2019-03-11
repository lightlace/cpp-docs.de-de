---
title: 'Vorgehensweise: Marshallen von Arrays mit PInvoke'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
ms.openlocfilehash: 60b49135928e3dadffc2a3c7a422646d2f3a768d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57752310"
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>Vorgehensweise: Marshallen von Arrays mit PInvoke

In diesem Thema wird erläutert, wie native Funktionen, akzeptieren die Zeichenfolgen im C-Stil können aufgerufen werden, mit dem CLR-String-Datentyp <xref:System.String> mit Plattformaufruf von .NET Framework-Unterstützung. Visual C++-Programmierer werden empfohlen, stattdessen die C++-Interop-Funktionen (wenn möglich), da der P/Invoke bietet wenig Fehler während der Kompilierung, berichterstellung, ist nicht typsicher, und kann einfacher zu implementieren. Wenn die nicht verwaltete API wird als DLL verpackt, und der Quellcode nicht verfügbar ist, wird P/Invoke ist die einzige Option (andernfalls finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)).

## <a name="example"></a>Beispiel

Da die systemeigenen und verwalteten Arrays anders als im Arbeitsspeicher angeordnet werden, erfordert die erfolgreiche Übergabe über die verwaltete/nicht verwaltete Grenze Konvertierung oder Marshalling. In diesem Thema wird veranschaulicht, wie ein Array von Elementen der einfachen (blitfähigen) nativer Funktionen aus verwaltetem Code übergeben werden kann.

Wie in der verwalteten und nicht verwalteten Daten-Marshalling im Allgemeinen ist die <xref:System.Runtime.InteropServices.DllImportAttribute> Attribut wird verwendet, um einen verwalteten Einstiegspunkt für jede systemeigene Funktion erstellen, die verwendet werden. Im Fall von Funktionen, die Arrays als Argumente akzeptieren die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut muss ebenfalls verwendet werden, um dem Compiler anzugeben, wie die Daten gemarshallt werden. Im folgenden Beispiel die <xref:System.Runtime.InteropServices.UnmanagedType> Enumeration wird verwendet, um anzugeben, dass das verwaltete Array als Array im C-Stil gemarshallt wird.

Der folgende Code besteht aus einer nicht verwalteten und ein verwaltetes Modul. Das nicht verwaltete Modul handelt es sich um eine DLL, die eine Funktion definiert, die ein Array von Ganzzahlen akzeptiert. Das zweite Modul ist eine verwaltete-befehlszeilenanwendung, die dieser Funktion können importiert, aber in Bezug auf ein verwaltetes Array definiert und verwendet die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut, um anzugeben, dass das Array in ein systemeigenes Array beim Aufruf konvertiert werden soll.

Das verwaltete Modul wird mit "/ CLR" kompiliert.

```cpp
// TraditionalDll4.cpp
// compile with: /LD /EHsc
#include <iostream>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);
}

void TakesAnArray(int len, int a[]) {
   printf_s("[unmanaged]\n");
   for (int i=0; i<len; i++)
      printf("%d = %d\n", i, a[i]);
}
```

```cpp
// MarshalBlitArray.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL {
   [DllImport("TraditionalDLL4.dll")]
   static public void TakesAnArray(
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);
};

int main() {
   array<int>^ b = gcnew array<int>(3);
   b[0] = 11;
   b[1] = 33;
   b[2] = 55;
   TraditionalDLL::TakesAnArray(3, b);

   Console::WriteLine("[managed]");
   for (int i=0; i<3; i++)
      Console::WriteLine("{0} = {1}", i, b[i]);
}
```

Beachten Sie, dass kein Teil der DLL verfügbar, auf den verwalteten Code mithilfe der herkömmlichen gemacht wird #include-Anweisung. In der Tat, da die DLL nur zur Laufzeit zugegriffen wird, Probleme mit Funktionen mit importiert <xref:System.Runtime.InteropServices.DllImportAttribute> zum Zeitpunkt der Kompilierung nicht erkannt.

## <a name="see-also"></a>Siehe auch

[Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
