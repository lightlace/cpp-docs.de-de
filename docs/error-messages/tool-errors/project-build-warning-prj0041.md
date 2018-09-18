---
title: Projektbuildwarnung PRJ0041 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7677c5718783065f64e52f98f7ddbed76e905d2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038138"
---
# <a name="project-build-warning-prj0041"></a>Projektbuildwarnung PRJ0041

Kann nicht gefunden werden fehlende Abhängigkeit 'Abhängigkeit' Datei 'File'. Das Projekt kann zwar erstellt, ist aber nicht mehr aktuell angezeigt werden, bis diese Datei gefunden wird.

Eine Datei (Ressourcendatei oder.idl/.odl-Datei, z. B. enthalten eine Include-Anweisung, die das Projektsystem nicht aufgelöst werden kann konnte.

Da das Projektsystem präprozessoranweisungen (z. B. "#if") nicht verarbeitet, kann die problematische Anweisung kein Teil des Builds sein.

Um diese Warnung zu beheben, löschen Sie alle unnötigen Code in der RC-Dateien, oder fügen Sie die Platzhalterdateien mit dem entsprechenden Namen.