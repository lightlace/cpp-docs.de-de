---
title: Compilerwarnung (Stufe 3) C4197
ms.date: 11/04/2016
f1_keywords:
- C4197
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
ms.openlocfilehash: 15b2fba94bfc956775a1e454893e7509a32000e5
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522622"
---
# <a name="compiler-warning-level-3-c4197"></a>Compilerwarnung (Stufe 3) C4197

"Type": Flüchtige höchste Ebene bei Umwandlung wird ignoriert.

Der Compiler hat eine Typumwandlung in einem mit gekennzeichneten [flüchtige](../../cpp/volatile-cpp.md), oder eine Typumwandlung eines r-Typs zu einem Typ, der mit permanenten qualifiziert wird. Gemäß dem C-standard (6.5.3) sind die vollqualifizierten Typen zugeordnete Eigenschaften nur für die l-Wert-Ausdrücken von Bedeutung.

Im folgende Beispiel wird die C4197 generiert:

```
// C4197.cpp
// compile with: /W3
#include <stdio.h>
#include <signal.h>
#include <stdlib.h>

void sigproc(int);
struct S
{
   int i;
} s;

int main()
{
   signal(SIGINT, sigproc);
   s.i = 1;
   S *pS = &s;
   for ( ; (volatile int)pS->i ; )   // C4197
      break;
   // for ( ; *(volatile int *)&pS->i ; )   // OK
   //    break;
}

void sigproc(int) // ctrl-C
{
   signal(SIGINT, sigproc);
   s.i = 0;
}
```