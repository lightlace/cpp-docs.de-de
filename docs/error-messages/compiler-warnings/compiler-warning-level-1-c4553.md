---
title: Compilerwarnung (Stufe 1) C4553
ms.date: 11/04/2016
f1_keywords:
- C4553
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
ms.openlocfilehash: 7a299d4a99818699e9be31e7d15d9e589de05c15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410342"
---
# <a name="compiler-warning-level-1-c4553"></a>Compilerwarnung (Stufe 1) C4553

'Operator': Operator hat keine Auswirkungen; Wollten Sie "Operator"?

Wenn eine Ausdrucksanweisung einen Operator mit keine ungünstigen Nebeneffekte wie am Anfang des Ausdrucks, ist es wahrscheinlich einen Fehler.

Im folgende Beispiel wird die C4553 generiert:

```
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```