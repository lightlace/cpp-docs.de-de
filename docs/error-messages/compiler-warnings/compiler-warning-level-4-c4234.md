---
title: Compilerwarnung (Stufe 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 63a22fed0832677837eb786268fc92946d295b79
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541777"
---
# <a name="compiler-warning-level-4-c4234"></a>Compilerwarnung (Stufe 4) C4234

nicht dem Standard entsprechende Erweiterung: Schlüsselwort Schlüsselwort für zukünftige Verwendung reserviert

Der Compiler implementiert noch nicht das Schlüsselwort, das Sie verwendet haben.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warnung](../../preprocessor/warning.md). Wenn Sie z. b. C4234 zu einem Warnungs Problem auf der Ebene 4 machen möchten,

```cpp
#pragma warning(2:4234)
```

in der Quellcodedatei.