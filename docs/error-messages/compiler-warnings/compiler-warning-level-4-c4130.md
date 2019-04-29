---
title: Compilerwarnung (Stufe 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: 1b1fb72d68309a4bef56ccd844ad30d967bbadbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401311"
---
# <a name="compiler-warning-level-4-c4130"></a>Compilerwarnung (Stufe 4) C4130

"Operator": Logische Operation mit Adresse einer Zeichenfolgenkonstanten

Das Verwenden des Operators mit der Adresse eines Zeichenfolgenliterals erzeugt unerwarteten Code.

Im folgenden Beispiel wird C4130 generiert.

```
// C4130.cpp
// compile with: /W4
int main()
{
   char *pc;
   pc = "Hello";
   if (pc == "Hello") // C4130
   {
   }
}
```

Die **if** -Anweisung vergleicht den im Zeiger `pc` gespeicherten Wert mit der Adresse der Zeichenfolge "Hello", die bei jedem Vorkommen der Zeichenfolge im Code separat zugewiesen wird. Die **if** Anweisung vergleicht nicht die Zeichenfolge, auf die von `pc` gezeigt wird, mit der Zeichenfolge "Hello".

Verwenden Sie zum Vergleichen von Zeichenfolgen die `strcmp` -Funktion.