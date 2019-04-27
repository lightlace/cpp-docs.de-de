---
title: Compilerwarnung (Stufe 1) C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: c737a48883b97970af70014e2bda4bdc508ab471
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207567"
---
# <a name="compiler-warning-level-1-c4228"></a>Compilerwarnung (Stufe 1) C4228

nicht dem Standard entsprechende Erweiterung: Qualifizierer nach einem Komma in der Deklaratorliste werden ignoriert.

Verwenden von Qualifizierern wie **const** oder `volatile` nach dem Komma beim Deklarieren von Variablen eine Microsoft-Erweiterung ist ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Beispiel

```
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```