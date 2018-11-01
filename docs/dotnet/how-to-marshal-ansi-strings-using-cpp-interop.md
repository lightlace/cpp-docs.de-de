---
title: 'Gewusst wie: Marshallen von ANSI-Zeichenfolgen mit C++-Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
ms.openlocfilehash: 272e64a5dd8faf103daf3ab7fa17449bf3dbb7ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570497"
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>Gewusst wie: Marshallen von ANSI-Zeichenfolgen mit C++-Interop

In diesem Thema wird veranschaulicht, wie von ANSI-Zeichenfolgen werden können mithilfe C++-Interop, aber auf .NET Framework übergeben <xref:System.String> Zeichenfolgen im Unicode-Format darstellt, damit die Konvertierung in ANSI ein zusätzlicher Schritt ist. Für die Interoperation mit anderen Zeichenfolgen-Datentypen, finden Sie unter den folgenden Themen:

- [Vorgehensweise: Marshallen von Unicode-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von COM-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

Im folgenden code, Beispiele für die Verwendung der [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Anweisungen zum Implementieren verwaltet und nicht verwaltete Funktionen in der gleichen Datei, aber diese Funktionen auf die gleiche Weise interagieren, wenn in separaten Dateien definiert. Da Dateien, die ausschließlich nicht verwaltete Funktionen nicht mit kompiliert werden müssen [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md), behalten sie ihre Leistungsmerkmale.

## <a name="example"></a>Beispiel

Im Beispiel wird eine ANSI-Zeichenfolge von einer verwalteten übergeben, um eine nicht verwaltete Funktion mit <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>. Diese Methode belegt Speicher für den nicht verwalteten Heap und gibt die Adresse nach dem Ausführen der Konvertierung zurück. Dies bedeutet, dass kein anheften erforderlich ist (da es sich um eine auf dem GC-Heap nicht an die nicht verwaltete Funktion übergeben wird) und von IntPtr zurückgegeben <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> muss explizit freigegeben werden oder Memory Leakage auftritt.

```
// MarshalANSI1.cpp
// compile with: /clr
#include <iostream>
#include <stdio.h>

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(const char* p) {
   printf_s("(native) received '%s'\n", p);
}

#pragma managed

int main() {
   String^ s = gcnew String("sample string");
   IntPtr ip = Marshal::StringToHGlobalAnsi(s);
   const char* str = static_cast<const char*>(ip.ToPointer());

   Console::WriteLine("(managed) passing string...");
   NativeTakesAString( str );

   Marshal::FreeHGlobal( ip );
}
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Marshalling von Daten erforderlich, um eine ANSI-Zeichenfolge in einer verwalteten Funktion zuzugreifen, die durch eine nicht verwaltete Funktion aufgerufen wird. Nach dem Empfang der systemeigenen Zeichenfolge, die verwaltete Funktion können sie direkt verwenden oder konvertieren Sie ihn in eine verwaltete Zeichenfolge mithilfe der <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> Methode, wie gezeigt.

```
// MarshalANSI2.cpp
// compile with: /clr
#include <iostream>
#include <vcclr.h>

using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedStringFunc(char* s) {
   String^ ms = Marshal::PtrToStringAnsi(static_cast<IntPtr>(s));
   Console::WriteLine("(managed): received '{0}'", ms);
}

#pragma unmanaged

void NativeProvidesAString() {
   cout << "(native) calling managed func...\n";
   ManagedStringFunc("test string");
}

#pragma managed

int main() {
   NativeProvidesAString();
}
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)