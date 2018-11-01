---
title: 'Gewusst wie: Marshallen von Funktionszeigern mit PInvoke'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
ms.openlocfilehash: 2f12c86b7e32955622a4a2c598d01057e303a329
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435606"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>Gewusst wie: Marshallen von Funktionszeigern mit PInvoke

In diesem Thema wird erläutert, wie verwaltete Delegaten kann anstelle von Funktionszeigern verwendet werden, wenn Sie Funktionen mithilfe von .NET Framework P/Invoke-Funktionen Zusammenwirken mit nicht verwaltet werden. Visual C++-Programmierer sind jedoch empfohlen, stattdessen die C++-Interop-Funktionen (wenn möglich), da der P/Invoke bietet wenig Fehler während der Kompilierung, berichterstellung, ist nicht typsicher, und kann einfacher zu implementieren. Wenn die nicht verwaltete API wird als DLL verpackt, und der Quellcode nicht verfügbar ist, ist P/Invoke die einzige Option. Andernfalls finden Sie unter den folgenden Themen:

- [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Vorgehensweise: Marshallen von Rückrufen und Delegaten mit C++-Interop](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

Nicht verwaltete APIs, die Funktionszeiger verwenden, wie Argumente aus verwaltetem Code mit einem verwalteten Delegaten anstelle der systemeigenen Funktionszeiger aufgerufen werden können. Der Compiler automatisch der Delegat, der nicht verwalteten Funktionen als Funktionszeiger gemarshallt, und fügt den erforderlichen Übergang mit verwaltetem/nicht verwaltetem Code.

## <a name="example"></a>Beispiel

Der folgende Code besteht aus einer nicht verwalteten und ein verwaltetes Modul. Das nicht verwaltete Modul handelt es sich um eine DLL, die eine Funktion namens TakesCallback, die einen Funktionszeiger akzeptiert definiert. Diese Adresse wird verwendet, um die Ausführung der Funktion.

Das verwaltete Modul definiert einen Delegaten, die auf den systemeigenen Code als Funktionszeiger gemarshallt wird, und verwendet die <xref:System.Runtime.InteropServices.DllImportAttribute> Attribut, um die systemeigenen TakesCallback-Funktion für den verwalteten Code verfügbar zu machen. In der main-Funktion ist eine Instanz des Delegaten erstellt und an die TakesCallback-Funktion übergeben. Die Ausgabe zeigt, dass es sich bei dieser Funktion, die von der nativen TakesCallback-Funktion ausgeführt wird.

Die verwaltete Funktion unterdrückt Garbagecollection für die verwalteten Delegaten, um zu verhindern, dass .NET Framework Garbagecollection des Delegaten verschieben, während die systemeigene Funktion ausgeführt wird.

```cpp
// TraditionalDll5.cpp
// compile with: /LD /EHsc
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   /* Declare an unmanaged function type that takes two int arguments
      Note the use of __stdcall for compatibility with managed code */
   typedef int (__stdcall *CALLBACK)(int);
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);
}

int TakesCallback(CALLBACK fp, int n) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n);
}
```

```cpp
// MarshalDelegate.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

public delegate int GetTheAnswerDelegate(int);
public value struct TraditionalDLL {
   [DllImport("TraditionalDLL5.dll")]
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);
};

int GetNumber(int n) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;
   return x + n;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TraditionalDLL::TakesCallback(fp, 42);
}
```

Beachten Sie, dass kein Teil der DLL verfügbar gemacht wird, auf den verwalteten Code mithilfe der herkömmlichen #include-Anweisung. Tatsächlich ist die DLL zur Laufzeit nur zugegriffen, damit Probleme mit Funktionen mit importiert <xref:System.Runtime.InteropServices.DllImportAttribute> zum Zeitpunkt der Kompilierung nicht erkannt.

## <a name="see-also"></a>Siehe auch

[Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)