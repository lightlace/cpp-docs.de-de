---
title: Compilerwarnung (Stufe 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: f1e85591d8ec989d806eb43a6be99bdb1dc62fb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659328"
---
# <a name="compiler-warning-level-4-c4211"></a>Compilerwarnung (Stufe 4) C4211

nicht dem Standard entsprechende Erweiterung: Neudefinition von Extern als statisch

Mit den Standard-Microsoft-Erweiterungen (/ Ze), können Sie definieren eine `extern` Bezeichner als **statische**.

## <a name="example"></a>Beispiel

```
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

Derartige Neudefinitionen sind ungültig, ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="see-also"></a>Siehe auch

