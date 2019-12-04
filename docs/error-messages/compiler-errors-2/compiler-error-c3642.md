---
title: Compilerfehler C3642
ms.date: 11/04/2016
f1_keywords:
- C3642
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
ms.openlocfilehash: 7c3f9f05bf04c9a1c20fff7910836e7b50468a8e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742456"
---
# <a name="compiler-error-c3642"></a>Compilerfehler C3642

"return_type/args": eine Funktion kann nicht mit __clrcall Aufruf Konvention aus System eigenem Code aufgerufen werden.

Eine Funktion, die mit der [__clrcall](../../cpp/clrcall.md) -Aufruf Konvention gekennzeichnet ist, kann nicht von System eigenem (nicht verwaltetem) Code aufgerufen werden.

*return_type/args* ist entweder der Name der Funktion oder der Typ der `__clrcall` Funktion, die Sie aufzurufen versuchen.  Ein-Typ wird verwendet, wenn Sie über einen Funktionszeiger aufrufen.

Um eine verwaltete Funktion aus einem systemeigenen Kontext aufzurufen, können Sie eine Wrapper Funktion hinzufügen, die die `__clrcall`-Funktion aufruft. Oder Sie können den CLR-marshalling-Mechanismus verwenden. Weitere Informationen finden [Sie unter Gewusst wie: Mars Hallen von Funktions Zeigern mit PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) .

Im folgenden Beispiel wird C3642 generiert:

```cpp
// C3642.cpp
// compile with: /clr
using namespace System;
struct S {
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall
      Console::WriteLine(s);
   }
   void Test2(char * s) {
      Test(gcnew String(s));
   }
};

#pragma unmanaged
int main() {
   S s;
   s.Test("abc");   // C3642
   s.Test2("abc");   // OK
}
```
