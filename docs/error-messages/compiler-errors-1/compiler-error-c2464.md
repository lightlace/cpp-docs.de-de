---
title: Compilerfehler C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: a00ac997f73175eeab08a0132128e48e8fc58feb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498188"
---
# <a name="compiler-error-c2464"></a>Compilerfehler C2464

'Bezeichner': kann nicht "new" verwenden, um die Zuordnung eines Verweises

Eine Referenz-ID zugeordnet war die `new` Operator. Verweise sind also nicht Memory-Objekte, `new` kann keinen Zeiger darauf zurückgeben. Verwenden Sie die standard-Variablendeklaration-Syntax, um einen Verweis zu deklarieren.

Im folgende Beispiel wird die C2464 generiert:

```
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```