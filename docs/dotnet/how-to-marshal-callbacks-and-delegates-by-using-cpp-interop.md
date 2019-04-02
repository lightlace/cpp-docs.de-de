---
title: 'Vorgehensweise: Marshallen von Rückrufen und Delegaten mit C++-Interop'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
ms.openlocfilehash: f8088bf90162fd2177599c252b0eee6332d61289
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766936"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Vorgehensweise: Marshallen von Rückrufen und Delegaten mit C++-Interop

In diesem Thema wird veranschaulicht, das Marshallen von Rückrufen und Delegaten (die verwaltete Version eines Rückrufs) zwischen verwaltetem und nicht verwaltetem Code mithilfe von Visual C++.

Im folgenden code, Beispiele für die Verwendung der [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Anweisungen zum Implementieren verwaltet und nicht verwaltete Funktionen in der gleichen Datei, aber die Funktionen können auch in separaten Dateien definiert werden. Dateien, die ausschließlich nicht verwaltete Funktionen müssen nicht für die Kompilierung mit der [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie eine nicht verwaltete API, um einen verwalteten Delegaten ausgelöst wird. Ein verwalteter Delegat erstellt wird und eine der Interop-Methoden, <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, dient zum Abrufen des zugrunde liegenden Einstiegspunkts für den Delegaten. Diese Adresse wird dann an die nicht verwaltete Funktion übergeben bezeichneten ohne Kenntnis der Tatsache, dass es als eine verwaltete Funktion implementiert wird.

Beachten Sie, dass ist es möglich, aber nicht erforderlich ist, für das anheften der Delegat, der mit [Pin_ptr (C++ / CLI)](../extensions/pin-ptr-cpp-cli.md) um zu verhindern, dass er erneut befinden oder durch den Garbage Collector verworfen. Schutz vor der vorzeitigen Garbagecollection ist erforderlich, aber anheften bietet mehr Schutz als ist erforderlich, da es verhindert, Sammlung dass, verhindert aber zugleich verschieben.

Ein Delegat erneut durch eine Garbagecollection verschoben wird, wirkt sich nicht die zugrunde liegende verwaltete-Rückruf, also <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> wird verwendet, um einen Verweis auf den Delegaten, sodass Verschiebung des Delegaten, aber verhindert die Freigabe hinzufügen. Anstelle von GCHandle Pin_ptr reduziert die Fragmentierungspotenzial des verwalteten Heaps.

```
// MarshalDelegate1.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);

int TakesCallback(ANSWERCB fp, int n, int m) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n, m);
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   return n + m;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   GCHandle gch = GCHandle::Alloc(fp);
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

// force garbage collection cycle to prove
// that the delegate doesn't get disposed
   GC::Collect();

   int answer = TakesCallback(cb, 243, 257);

// release reference to delegate
   gch.Free();
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel ähnelt dem vorherigen Beispiel, aber in diesem Fall wird der Zeiger für die angegebene Funktion von der nicht verwalteten API gespeichert, damit er jederzeit aufgerufen werden kann, die erfordern, dass die automatische speicherbereinigung für einen beliebigen Zeitraum unterdrückt werden. Im folgenden Beispiel wird daher eine globale Instanz des <xref:System.Runtime.InteropServices.GCHandle> um zu verhindern, dass der Delegat wird der verschobene, unabhängig vom Gültigkeitsbereich der Funktion. Wie im ersten Beispiel erläutert wird, mithilfe von Pin_ptr ist nicht für diese Beispiele, aber in diesem Fall wäre nicht funktioniert dennoch wie der Gültigkeitsbereich der Pin_ptr auf eine einzelne Funktion beschränkt ist.

```
// MarshalDelegate2.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);
static ANSWERCB cb;

int TakesCallback(ANSWERCB fp, int n, int m) {
   cb = fp;
   if (cb) {
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);
      return cb(n, m);
   }
   printf_s("[unmanaged] unregistering callback");
   return 0;
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;

   return n + m + x;
}

static GCHandle gch;

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);

   gch = GCHandle::Alloc(fp);

   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TakesCallback(cb, 243, 257);

   // possibly much later (in another function)...

   Console::WriteLine("[managed] releasing callback mechanisms...");
   TakesCallback(0, 243, 257);
   gch.Free();
}
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
