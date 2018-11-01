---
title: Compilerfehler C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: 2bccd15b8c2b6d1c5cd6c4b536bbdaf350eb0181
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512904"
---
# <a name="compiler-error-c2081"></a>Compilerfehler C2081

'Bezeichner': Name in der formalen Parameterliste ist ungültig

Der Bezeichner verursacht einen Syntaxfehler.

Dieser Fehler kann verursacht werden, mithilfe des alten Stils für die Liste der formalen Parameter. Sie müssen den Typ der formalen Parameter in der Liste der formalen Parameter angeben.

Im folgende Beispiel wird die C2081 generiert:

```
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

Mögliche Lösung:

```
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```