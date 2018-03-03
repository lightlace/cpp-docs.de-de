---
title: Linkertoolwarnung Lnk4206 | Microsoft Docs
ms.date: 12/05/2017
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4206
dev_langs:
- C++
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd13ac59aefa074db869f0502743c7a49d23082c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4206"></a>Linkertoolwarnung LNK4206

> Vorkompilierte Typinformationen nicht gefunden; "*Filename*' nicht verknüpft oder überschrieben; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären

Die *Filename* kompilierte Objektdatei wird, mithilfe von ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md), wurde entweder nicht im LINK-Befehl angegeben oder überschrieben wurde.

Ein übliches Szenario für diese Warnung wird in einer Bibliothek wird die obj, die mit/Yc kompiliert wurde und auf denen keine Symbolverweise auf diese OBJ-Datei aus Ihrem Code vorhanden sind.  In diesem Fall der Linker nicht verwenden (oder sogar finden Sie unter) die OBJ-Datei.  In diesem Fall sollten Sie Ihr Code neu kompilieren und verwenden [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) für die Objekte, die mithilfe von kompiliert ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md).