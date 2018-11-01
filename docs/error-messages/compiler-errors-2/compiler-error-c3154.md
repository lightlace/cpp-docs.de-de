---
title: Compilerfehler C3154
ms.date: 11/04/2016
f1_keywords:
- C3154
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
ms.openlocfilehash: d14b921afa3888f1a9497f19bfeaa013b147b086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430549"
---
# <a name="compiler-error-c3154"></a>Compilerfehler C3154

Erwartet ',', bevor Sie mit den Auslassungspunkten. Nicht durch Trennzeichen getrennt, mit den Auslassungspunkten für Parameterarrayfunktionen nicht unterstützt wird.

Eine Funktion mit Variablen Argumenten wurde nicht ordnungsgemäß deklariert.

Weitere Informationen finden Sie unter [Variablenargumentlisten (...) (C++ / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3154 generiert.

```
// C3154.cpp
// compile with: /clr
ref struct R {
   void Func(int ... array<int> ^);   // C3154
   void Func2(int i, ... array<int> ^){}   // OK
   void Func3(array<int> ^){}   // OK
   void Func4(... array<int> ^){}   // OK
};

int main() {
   R ^ r = gcnew R;
   r->Func4(1,2,3);
}
```