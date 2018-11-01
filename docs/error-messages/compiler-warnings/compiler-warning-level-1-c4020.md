---
title: Compilerwarnung (Stufe 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 75148c210ddd2a611061d58c036d12c084f442cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482029"
---
# <a name="compiler-warning-level-1-c4020"></a>Compilerwarnung (Stufe 1) C4020

'Funktion': zu viele übergebene Parameter

Die Anzahl der tatsächlichen Parameter in einem Funktionsaufruf überschreitet die Anzahl der formalen Parameter in der Funktionsprototyp oder Definition vor. Der Compiler übergibt die zusätzlich übergebenen Parameter entsprechend der Aufrufkonvention der Funktion.

Im folgende Beispiel wird die C4020 generiert:

```
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

Mögliche Lösung:

```
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```