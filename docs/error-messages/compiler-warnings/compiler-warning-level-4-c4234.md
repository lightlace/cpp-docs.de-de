---
title: Compilerwarnung (Stufe 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 314ee068fb2be6148304360b0aaa3bd8029c283b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401071"
---
# <a name="compiler-warning-level-4-c4234"></a>Compilerwarnung (Stufe 4) C4234

nicht dem Standard entsprechende Erweiterung: ' Schlüsselwort ' für die zukünftige Verwendung reserviert

Der Compiler implementiert nicht noch das Schlüsselwort, die, das Sie verwendet.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma-Warnung](../../preprocessor/warning.md). Geben Sie beispielsweise Folgendes ein, um C4234 in eine Warnung der Stufe 4 zu machen,

```
#pragma warning(2:4234)
```

in der Quellcodedatei.