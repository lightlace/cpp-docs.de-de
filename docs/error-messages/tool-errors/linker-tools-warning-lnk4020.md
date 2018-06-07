---
title: Warnung LNK4020 der Linkertools | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4020
dev_langs:
- C++
helpviewer_keywords:
- LNK4020
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e55239b90910f6c151949c53939d4f8ed7c15c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570692"
---
# <a name="linker-tools-warning-lnk4020"></a>Linkertoolwarnung LNK4020

> Typeneinträge in "*Filename*" ist beschädigt; einige Symbole und Typen möglicherweise nicht über den Debugger zugegriffen werden

Die PDB-Datei *Filename* Typeneinträge beschädigt wurde.

Dieses Problem tritt häufig auf andere Buildprobleme sekundären; Wenn dies das erste gemeldeten Buildproblem ist, die andere Fehler und Warnungen zurecht erste. Wenn dieses ersten gemeldeten Problem vorliegt, müssen Sie möglicherweise bereinigen Ihre Buildverzeichnisse, und erstellen Sie das Projekt neu. Wenn Sie parallele Buildprozesse verwenden, finden Sie, wenn der Fehler weiterhin auftritt, wenn Sie Ihren Build serialisieren.