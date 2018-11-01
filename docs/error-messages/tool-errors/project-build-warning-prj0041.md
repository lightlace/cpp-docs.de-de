---
title: Projektbuildwarnung PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: b0fceff05ffe35515965b7e0a880c8b4c941b07e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583208"
---
# <a name="project-build-warning-prj0041"></a>Projektbuildwarnung PRJ0041

Kann nicht gefunden werden fehlende Abhängigkeit 'Abhängigkeit' Datei 'File'. Das Projekt kann zwar erstellt, ist aber nicht mehr aktuell angezeigt werden, bis diese Datei gefunden wird.

Eine Datei (Ressourcendatei oder.idl/.odl-Datei, z. B. enthalten eine Include-Anweisung, die das Projektsystem nicht aufgelöst werden kann konnte.

Da das Projektsystem präprozessoranweisungen (z. B. "#if") nicht verarbeitet, kann die problematische Anweisung kein Teil des Builds sein.

Um diese Warnung zu beheben, löschen Sie alle unnötigen Code in der RC-Dateien, oder fügen Sie die Platzhalterdateien mit dem entsprechenden Namen.