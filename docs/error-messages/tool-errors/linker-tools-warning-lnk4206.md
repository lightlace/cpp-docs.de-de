---
title: Linkertoolwarnung LNK4206
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: dc81df89609f59834c8a3271dd64f3b99b281f90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613637"
---
# <a name="linker-tools-warning-lnk4206"></a>Linkertoolwarnung LNK4206

> Vorkompilierte Typinformationen nicht gefunden. "*Filename*' nicht verknüpft oder überschrieben; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären

Die *Filename* kompilierte Objektdatei wird, mithilfe von ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md), wurde entweder im LINK-Befehl nicht angegeben oder überschrieben.

Ein häufiges Szenario für diese Warnung ist die .obj, die mit/Yc kompiliert wurde in einer Bibliothek, und es sind keine Symbolverweise auf diese OBJ-Datei aus Ihrem Code.  In diesem Fall der Linker keine (oder sogar) die OBJ-Datei.  In diesem Fall sollten Sie Ihren Code neu kompilieren und verwenden [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) für die Objekte, die mit kompiliert ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md).