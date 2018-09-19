---
title: Projektbuildfehler prj0003 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0003
dev_langs:
- C++
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d1a23b8171c916b05df1d715f803893ab0720e6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053816"
---
# <a name="project-build-error-prj0003"></a>Projektbuildfehler PRJ0003

> Fehler beim Erstellen des "*Befehlszeile*".

Die *Befehlszeile* Befehl formatiert wird, mit der Eingabe in die **Eigenschaftenseiten** Dialogfeld hat einen Fehlercode zurückgegeben, aber keine Informationen angezeigt, der **Ausgabe** Fenster.

Mögliche Ursachen für diesen Fehler sind:

- Ihr Projekt hängt von ATL-Server ab. Ab Visual Studio 2008, ATL-Server ist nicht mehr als Teil von Visual Studio enthalten, jedoch wurde als shared-Source-Projekt auf CodePlex veröffentlicht. Um den Quellcode für die ATL-Server und die Tools herunterzuladen, wechseln Sie zu [ATL-Serverbibliothek und Tools](http://go.microsoft.com/fwlink/p/?linkid=81979).

- Geringe Systemressourcen. Schließen Sie einige Anwendungen zur Lösung dieses Problems.

- Unzureichender Sicherheitsberechtigungen. Stellen Sie sicher, dass Sie über die erforderlichen Sicherheitsrechte verfügen.

- Die ausführbare Datei im angegebenen Pfade **VC++-Verzeichnisse** enthalten nicht den Pfad für das Tool, das Sie ausführen möchten. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)

- Für Makefile-Projekte, fehlt einen Befehl für die Ausführung **Buildbefehlszeile** oder **neu erstellte Befehlszeile**.

## <a name="see-also"></a>Siehe auch

[Projektbuildfehler und -warnungen (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)