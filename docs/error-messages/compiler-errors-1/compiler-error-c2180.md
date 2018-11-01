---
title: Compilerfehler C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 16fcf15eb29743f74bbf2edcb1016f2e15228e5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553317"
---
# <a name="compiler-error-c2180"></a>Compilerfehler C2180

steuernder Ausdruck ist vom Typ "type".

Der steuernde Ausdruck in eine `if`-, `while`- oder `for`-Anweisung, oder die `do`-Anweisung ist ein konvertierter Ausdruck für `void`. Um dieses Problem zu beheben, ändern Sie den steuernden Ausdruck so, dass er einen `bool`-Typ oder einen Typ erstellt, der in `bool` konvertiert werden kann.

Im folgenden Beispiel wird C2180 generiert:

```
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```