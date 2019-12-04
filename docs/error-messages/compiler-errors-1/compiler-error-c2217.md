---
title: Compilerfehler C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: 7417c651fde6bef781bb6eb2e081cd3ad8ecc3a0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741299"
---
# <a name="compiler-error-c2217"></a>Compilerfehler C2217

"attribute1" erfordert "attribute2".

Das erste Funktions Attribut erfordert das zweite Attribut.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Die als `near`deklarierte Interruptfunktion (`__interrupt`). Interrupt-Funktionen müssen `far`werden.

1. Mit `__stdcall`deklarierte Interruptfunktion oder `__fastcall`. Interrupt-Funktionen müssen C-Aufruf Konventionen verwenden.

## <a name="example"></a>Beispiel

C2217 kann auch auftreten, wenn Sie versuchen, einen Delegaten an eine CLR-Funktion zu binden, die eine Variable Anzahl von Argumenten annimmt. Wenn die Funktion auch über eine e-param-Array Überladung verfügt, verwenden Sie diese stattdessen. Im folgenden Beispiel wird C2217 generiert.

```cpp
// C2217.cpp
// compile with: /clr
using namespace System;
delegate void MyDel(String^, Object^, Object^, ...);   // C2217
delegate void MyDel2(String ^, array<Object ^> ^);   // OK

int main() {
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);
   array<Object ^ > ^ x = gcnew array<Object ^>(2);
   x[0] = safe_cast<Object^>(0);
   x[1] = safe_cast<Object^>(1);

   // wl("{0}, {1}", 0, 1);
   wl("{0}, {1}", x);
}
```
