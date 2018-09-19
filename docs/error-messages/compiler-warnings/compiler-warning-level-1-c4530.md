---
title: Compilerwarnung (Stufe 1) C4530 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4530
dev_langs:
- C++
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbfbc67377dd48eeb692bdd4cac1f113fbdf7f6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110457"
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