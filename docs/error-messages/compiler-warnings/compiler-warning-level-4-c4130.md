---
title: Compilerwarnung (Stufe 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: b55594608eccc5d1e5e764bffb73ecb3787af1e4
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541594"
---
# <a name="compiler-warning-level-4-c4130"></a>Compilerwarnung (Stufe 4) C4130

"Operator": Logische Operation mit Adresse einer Zeichenfolgenkonstanten

Das Verwenden des Operators mit der Adresse eines Zeichenfolgenliterals erzeugt unerwarteten Code.

Im folgenden Beispiel wird C4130 generiert.

```cpp
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