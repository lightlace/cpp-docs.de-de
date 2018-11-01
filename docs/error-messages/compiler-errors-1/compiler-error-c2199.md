---
title: Compilerfehler C2199
ms.date: 11/04/2016
f1_keywords:
- C2199
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
ms.openlocfilehash: e5892a537cbf337b23ff2356583cec4bf5925677
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530971"
---
# <a name="compiler-error-c2199"></a>Compilerfehler C2199

Syntaxfehler: gefunden ' Bezeichner ("im globalen Gültigkeitsbereich (war eine Deklaration beabsichtigt?)

Der angegebene Kontext verursachte einen Syntaxfehler. Es gibt möglicherweise falsche-Deklarationssyntax.

Im folgende Beispiel wird die C2199 generiert:

```
// C2199.cpp
// compile with: /c
int j = int(1) int(1);   // C2199
int j = 1;   // OK
```