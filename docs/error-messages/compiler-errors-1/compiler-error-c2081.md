---
title: Compilerfehler C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: 2e8e813d8162b9a191b6760366b52783e7c8609f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301989"
---
# <a name="compiler-error-c2081"></a>Compilerfehler C2081

"Identifier": der Name in der formalen Parameterliste ist ungültig.

Der Bezeichner hat einen Syntax Fehler verursacht.

Dieser Fehler kann dadurch verursacht werden, dass der alte Stil für die Liste formaler Parameter verwendet wird. Sie müssen den Typ der formalen Parameter in der Liste formaler Parameter angeben.

Im folgenden Beispiel wird C2081 generiert:

```c
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

Mögliche Lösung:

```c
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```
