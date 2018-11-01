---
title: Compilerwarnung (Stufe 1) C4530
ms.date: 11/04/2016
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: a542f9b6bb73e561592e1e779aa6ee493612e6ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554093"
---
# <a name="compiler-warning-level-1-c4530"></a>Compilerwarnung (Stufe 1) C4530

C++-Handler verwendet, aber Entladesemantik sind nicht aktiviert. Geben Sie/EHsc

C++-Ausnahmebehandlung verwendet wurde, aber [/EHsc](../../build/reference/eh-exception-handling-model.md) wurde nicht ausgewählt.

Wenn die Option/EHsc nicht aktiviert wurde, wird ein Objekt mit automatischem Speicher im Bereich zwischen der Funktion, die dies ausgelöst und die Funktion ausgelöst, Abfangen nicht zerstört werden. Ein Objekt mit automatischem Speicher jedoch erstellt, eine **versuchen Sie es** oder **catch** Block wird zerstört werden.

Im folgende Beispiel wird die C4530 generiert:

```
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

Kompilieren Sie das Beispiel mit/EHsc, um die Warnung zu beheben.