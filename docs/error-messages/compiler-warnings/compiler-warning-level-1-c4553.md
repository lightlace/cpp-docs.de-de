---
title: Compilerwarnung (Stufe 1) C4553 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4553
dev_langs:
- C++
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17c5887b550ea3181ac51d23ee24928502da1003
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096430"
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