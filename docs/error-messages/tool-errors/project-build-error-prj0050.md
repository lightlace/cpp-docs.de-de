---
title: Projektbuildfehler PRJ0050 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0050
dev_langs:
- C++
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb3949ea0db2f1667aecf1aeeefd922b192cbf41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100590"
---
# <a name="project-build-error-prj0050"></a>Projektbuildfehler PRJ0050

Fehler beim Registrieren der Ausgabe. Stellen Sie sicher, dass Sie die entsprechenden Berechtigungen zum Ändern der Registrierung haben.

Das Visual C++-Buildsystem konnte nicht aus, um die Ausgabe des Builds (Dll oder .exe) zu registrieren. Sie müssen als Administrator zum Ändern der Registrierung angemeldet sein.

Wenn Sie eine DLL-Datei erstellen, können Sie versuchen, registrieren Sie die DLL-Datei manuell mit regsvr32.exe, dies sollte angezeigt werden Informationen, warum der Build fehlgeschlagen ist.

Wenn Sie eine DLL-Datei nicht erstellen, betrachten Sie das Buildprotokoll für den Befehl aus, der einen Fehler verursacht hat.