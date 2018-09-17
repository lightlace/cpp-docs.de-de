---
title: Ziele in mehreren Beschreibungsblöcken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- blocks, multiple description
- multiple description blocks
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f339561e0a1e8c94063aa0c36c3ecbc96545b35f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722773"
---
# <a name="targets-in-multiple-description-blocks"></a>Ziele in mehreren Beschreibungsblöcken

Geben Sie zwei aufeinander folgende Doppelpunkte (:) zwischen den Zielen und abhängigen Dateien, um ein Ziel in mehreren Beschreibungsblöcken mit verschiedenen Befehlen zu aktualisieren.

```
target.lib :: one.asm two.asm three.asm
    ml one.asm two.asm three.asm
    lib target one.obj two.obj three.obj
target.lib :: four.c five.c
    cl /c four.c five.c
    lib target four.obj five.obj
```

## <a name="see-also"></a>Siehe auch

[Ziele](../build/targets.md)