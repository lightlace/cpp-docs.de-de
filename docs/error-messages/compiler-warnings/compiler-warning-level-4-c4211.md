---
title: Compilerwarnung (Stufe 4) C4211 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4211
dev_langs:
- C++
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e38764970b8afde477c4f627e5cd3e5874d3b129
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054532"
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

