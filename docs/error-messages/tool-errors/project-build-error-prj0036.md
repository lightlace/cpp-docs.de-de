---
title: Projektbuildfehler PRJ0036
ms.date: 11/04/2016
f1_keywords:
- PRJ0036
helpviewer_keywords:
- PRJ0036
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
ms.openlocfilehash: 9b9232583c464548167e22d0104e0c6098093eab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435281"
---
# <a name="project-build-error-prj0036"></a>Projektbuildfehler PRJ0036

Die 'Additional Files'-Eigenschaft für das Web Deployment Tool enthalten einen ungültigen Eintrag.

Die Eigenschaft "zusätzliche Dateien" auf der Eigenschaftenseite für die Webbereitstellung enthalten einen Fehler, möglicherweise aufgrund eines Problems der Makro-Evaluierung. Dass der Pfad enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind falsch formatiert wurde, wird von dieser Fehler auch bedeuten.

Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.

Dieser Fehler kann auch bedeuten, dass eine der Dateien auf die verwiesen wird nicht vorhanden.