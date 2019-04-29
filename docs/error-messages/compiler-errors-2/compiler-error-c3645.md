---
title: Compilerfehler C3645
ms.date: 11/04/2016
f1_keywords:
- C3645
helpviewer_keywords:
- C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
ms.openlocfilehash: f733de6920e00f1f53c87884a7a334e575bceb06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385783"
---
# <a name="compiler-error-c3645"></a>Compilerfehler C3645

"Function": __clrcall kann nicht verwendet werden, auf die Funktionen, die in nativen Code kompiliert

Das Vorhandensein von Schlüsselwörtern in einer Funktion bewirkt, dass die Funktion in systemeigenem Code kompiliert werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3645 generiert.

```
// C3645.cpp
// compile with: /clr /c
#pragma unmanaged
int __clrcall dog() {}   // C3645
```