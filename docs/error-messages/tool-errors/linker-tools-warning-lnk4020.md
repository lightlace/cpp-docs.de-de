---
title: Linkertoolwarnung LNK4020
ms.date: 05/29/2018
f1_keywords:
- LNK4020
helpviewer_keywords:
- LNK4020
ms.openlocfilehash: 7810fd9a97a8f6e22ad362819a024358a9f4b07c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298580"
---
# <a name="linker-tools-warning-lnk4020"></a>Linkertoolwarnung LNK4020

> ein Typeneintrag in "*Filename*' ist beschädigt; einige Symbole und Typen möglicherweise nicht zugegriffen werden kann, aus dem Debugger

Die PDB-Datei *Filename* Typeneinträge beschädigt wurde.

Dieses Problem tritt häufig auf anderen Buildfehlern sekundären; es sei denn, dies das erste Buildproblem der gemeldeten ist, arbeiten Sie mit den anderen Fehlern und Warnungen erste. Ist dies das erste gemeldeten Problem, müssen Sie die Buildverzeichnisse zu bereinigen und Neuerstellen des Projekts. Wenn Sie parallele Buildprozesse verwenden, finden Sie, wenn der Fehler weiterhin auftritt, wenn Sie Ihren Build serialisieren.