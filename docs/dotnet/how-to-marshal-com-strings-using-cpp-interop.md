---
title: 'Vorgehensweise: Marshallen von COM-Zeichenfolgen mit C++-Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
ms.openlocfilehash: e86cf0b3e57eda9a0f4fa5fe2337d0c42de5669f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58780872"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Vorgehensweise: Marshallen von COM-Zeichenfolgen mit C++-Interop

In diesem Thema wird veranschaulicht, wie ein BSTR (das grundlegende Zeichenfolgenformat bevorzugt wird in COM-Programmierung) werden kann von einer verwalteten übergeben werden, um eine nicht verwaltete Funktion (und umgekehrt). Für die Interoperation mit anderen Zeichenfolgen-Datentypen, finden Sie unter den folgenden Themen:

- [Vorgehensweise: Marshallen von Unicode-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von ANSI-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

Im folgenden code, Beispiele für die Verwendung der [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Anweisungen zum Implementieren verwaltet und nicht verwaltete Funktionen in der gleichen Datei, aber diese Funktionen auf die gleiche Weise interagieren, wenn in separaten Dateien definiert. Dateien, die ausschließlich nicht verwaltete Funktionen müssen nicht für die Kompilierung mit [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie ein BSTR (einem Zeichenfolgenformat in COM-Programmierung verwendet) übergeben werden kann von einer verwalteten an eine nicht verwaltete Funktion. Der aufrufende verwaltete Funktion verwendet <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> zum Abrufen der Adresse einer BSTR-Darstellung des Inhalts des .NET System.String. This-Zeiger ist verknüpft mit [Pin_ptr (C++ / CLI)](../extensions/pin-ptr-cpp-cli.md) um sicherzustellen, dass die physische Adresse während einer Garbage Collection-Zyklus nicht geändert wird, während die nicht verwaltete Funktion ausgeführt wird. Der Garbage Collector ist nicht zulässig, verschieben Sie den Arbeitsspeicher, bis die [Pin_ptr (C++ / CLI)](../extensions/pin-ptr-cpp-cli.md) den Gültigkeitsbereich verlässt.

```
// MarshalBSTR1.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(BSTR bstr) {
   printf_s("%S", bstr);
}

#pragma managed

int main() {
   String^ s = "test string";

   IntPtr ip = Marshal::StringToBSTR(s);
   BSTR bs = static_cast<BSTR>(ip.ToPointer());
   pin_ptr<BSTR> b = &bs;

   NativeTakesAString( bs );
   Marshal::FreeBSTR(ip);
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie ein BSTR übergeben werden kann aus einer nicht verwalteten an eine nicht verwaltete Funktion. Der empfangenden verwaltete Funktion kann entweder verwenden Sie die Zeichenfolge in als BSTR oder verwenden <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> konvertiert eine <xref:System.String> für die Verwendung mit anderen verwaltete Funktionen. Da der Arbeitsspeicher, die das BSTR darstellt, die auf den nicht verwalteten Heap zugewiesen wird, ist kein anheften erforderlich, da keine Garbagecollection auf dem nicht verwalteten Heap vorhanden ist.

```
// MarshalBSTR2.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedTakesAString(BSTR bstr) {
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);
}

#pragma unmanaged

void UnManagedFunc() {
   BSTR bs = SysAllocString(L"test string");
   printf_s("(unmanaged) passing BSTR to managed func...\n");
   ManagedTakesAString(bs);
}

#pragma managed

int main() {
   UnManagedFunc();
}
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
