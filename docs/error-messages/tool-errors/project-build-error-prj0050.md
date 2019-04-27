---
title: Projektbuildfehler PRJ0050
ms.date: 11/04/2016
f1_keywords:
- PRJ0050
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
ms.openlocfilehash: ec2490bad70d2b2eb72cbb48771900f09f8c2f67
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226490"
---
# <a name="project-build-error-prj0050"></a>Projektbuildfehler PRJ0050

Fehler beim Registrieren der Ausgabe. Stellen Sie sicher, dass Sie die entsprechenden Berechtigungen zum Ändern der Registrierung haben.

Das Visual C++-Buildsystem konnte nicht aus, um die Ausgabe des Builds (Dll oder .exe) zu registrieren. Sie müssen als Administrator zum Ändern der Registrierung angemeldet sein.

Wenn Sie eine DLL-Datei erstellen, können Sie versuchen, registrieren Sie die DLL-Datei manuell mit regsvr32.exe, dies sollte angezeigt werden Informationen, warum der Build fehlgeschlagen ist.

Wenn Sie eine DLL-Datei nicht erstellen, betrachten Sie das Buildprotokoll für den Befehl aus, der einen Fehler verursacht hat.