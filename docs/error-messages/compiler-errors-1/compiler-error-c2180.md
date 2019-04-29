---
title: Compilerfehler C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 16fcf15eb29743f74bbf2edcb1016f2e15228e5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385913"
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