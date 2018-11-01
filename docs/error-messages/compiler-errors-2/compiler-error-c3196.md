---
title: Compilerfehler C3196
ms.date: 11/04/2016
f1_keywords:
- C3196
helpviewer_keywords:
- C3196
ms.assetid: d9c38a13-191d-472d-aa2b-f61a6459d16c
ms.openlocfilehash: 252fef18fa98183dcc75219c1b802461f3bd2833
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517051"
---
# <a name="compiler-error-c3196"></a>Compilerfehler C3196

'Schlüsselwort': mehrmals verwendet

Ein Schlüsselwort wurde mehr als einmal verwendet werden.

Im folgende Beispiel wird die C3196 generiert:

```
// C3196.cpp
// compile with: /clr
ref struct R abstract abstract {};   // C3196
ref struct S abstract {};   // OK
```