---
title: Compilerfehler C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 5e9444356e536a8369dbcf62cac3c7538d9da5dd
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301898"
---
# <a name="compiler-error-c2180"></a>Compilerfehler C2180

steuernder Ausdruck ist vom Typ "type".

Der steuernde Ausdruck in eine `if`-, `while`- oder `for`-Anweisung, oder die `do`-Anweisung ist ein konvertierter Ausdruck für `void`. Um dieses Problem zu beheben, ändern Sie den steuernden Ausdruck so, dass er einen `bool`-Typ oder einen Typ erstellt, der in `bool` konvertiert werden kann.

Im folgenden Beispiel wird C2180 generiert:

```c
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```
