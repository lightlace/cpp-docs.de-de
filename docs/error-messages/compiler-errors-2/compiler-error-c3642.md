---
title: Compilerfehler C3642
ms.date: 11/04/2016
f1_keywords:
- C3642
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
ms.openlocfilehash: d524c49075c400caa345dd26ed681734ea0cfb94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385615"
---
# <a name="compiler-error-c3642"></a>Compilerfehler C3642

"Return_type/Args": kann keine Funktion aufgerufen, mit der __clrcall-Aufrufkonvention aus systemeigenem Code

Eine Funktion, die mit der [__clrcall](../../cpp/clrcall.md) Aufrufkonvention kann nicht von systemeigenem (nicht verwalteten) Code aufgerufen werden.

*Return_type/Args* ist entweder der Name der Funktion oder den Typ des der `__clrcall` Funktion, die Sie aufrufen möchten.  Ein Typ wird verwendet, wenn Sie über einen Funktionszeiger aufrufen.

Um eine verwaltete Funktion aus einem systemeigenen Kontext aufzurufen, können Sie eine "Wrapper"-Funktion, die angerufen Hinzufügen der `__clrcall` Funktion. Sie können auch den CLR-marshalling-Mechanismus; finden Sie unter [Vorgehensweise: Marshallen von Funktion Zeigern mithilfe von PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) für Weitere Informationen.

Im folgende Beispiel wird die C3642 generiert:

```
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