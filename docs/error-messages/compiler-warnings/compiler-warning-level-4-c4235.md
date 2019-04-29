---
title: Compilerwarnung (Stufe 4) C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: 80ad388b26b2b972aa1301c1f335d0361a75f15f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401045"
---
# <a name="compiler-warning-level-4-c4235"></a>Compilerwarnung (Stufe 4) C4235

Nicht dem Standard entsprechende Erweiterung: Das Schlüsselwort 'Schlüsselwort' wird für diese Architektur nicht unterstützt

Das von Ihnen verwendete Schlüsselwort wird vom Compiler nicht unterstützt.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma-Warnung](../../preprocessor/warning.md). Um C4235 beispielsweise in eine Warnung der Stufe 2 umzuwandeln, verwenden Sie folgende Codezeile

```
#pragma warning(2:4235)
```

in der Quellcodedatei.