---
title: 'Vorgehensweise: Marshal Unicode Strings Using C++ Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
ms.openlocfilehash: 920f06bd2197315b11f239827de76eba9591bad5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742662"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>Vorgehensweise: Marshal Unicode Strings Using C++ Interop

In diesem Thema wird veranschaulicht, einen Aspekt der Visual C++-Interoperabilität. Weitere Informationen finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Im folgenden code, Beispiele für die Verwendung der [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Anweisungen zum Implementieren verwaltet und nicht verwaltete Funktionen in der gleichen Datei, aber diese Funktionen auf die gleiche Weise interagieren, wenn in separaten Dateien definiert. Dateien, die ausschließlich nicht verwaltete Funktionen müssen nicht für die Kompilierung mit [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md).

In diesem Thema wird veranschaulicht, wie Unicode-Zeichenfolgen werden, können von einer verwalteten übergeben werden, um eine nicht verwaltete Funktion (und umgekehrt). Für die Interoperation mit anderen Zeichenfolgen-Datentypen, finden Sie unter den folgenden Themen:

- [Vorgehensweise: Marshallen von ANSI-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von COM-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

## <a name="example"></a>Beispiel

Um eine Unicode-Zeichenfolge von einer verwalteten an eine nicht verwaltete Funktion übergeben werden soll, kann die PtrToStringChars-Funktion (deklariert in Vcclr.h) verwendet werden, Zugriff auf den Speicher, in dem die verwaltete Zeichenfolge gespeichert wird. Da diese Adresse an eine native Funktion übergeben wird, ist es wichtig, dass der Arbeitsspeicher mit angeheftet werden [Pin_ptr (C++ / CLI)](../windows/pin-ptr-cpp-cli.md) um zu verhindern, dass die Zeichenfolgendaten verschoben wird, sollte ein Garbage Collection-Zyklus stattfinden und der nicht verwaltete Funktion ausgeführt wird.

```
// MarshalUnicode1.cpp
// compile with: /clr
#include <iostream>
#include <stdio.h>
#include <vcclr.h>

using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(const wchar_t* p) {
   printf_s("(native) received '%S'\n", p);
}

#pragma managed

int main() {
   String^ s = gcnew String("test string");
   pin_ptr<const wchar_t> str = PtrToStringChars(s);

   Console::WriteLine("(managed) passing string to native func...");
   NativeTakesAString( str );
}
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Marshalling von Daten erforderlich, um eine Unicode-Zeichenfolge in einer verwalteten Funktion wird aufgerufen, indem Sie eine nicht verwaltete Funktion zuzugreifen. Die verwaltete Funktion, nach dem Empfang der systemeigenen Unicode-Zeichenfolge, konvertiert es in eine verwaltete Zeichenfolge mit der <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> Methode.

```
// MarshalUnicode2.cpp
// compile with: /clr
#include <iostream>

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedStringFunc(wchar_t* s) {
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);
   Console::WriteLine("(managed) received '{0}'", ms);
}

#pragma unmanaged

void NativeProvidesAString() {
   cout << "(unmanaged) calling managed func...\n";
   ManagedStringFunc(L"test string");
}

#pragma managed

int main() {
   NativeProvidesAString();
}
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
