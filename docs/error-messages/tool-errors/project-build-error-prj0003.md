---
title: Projektbuildfehler prj0003 | Microsoft Docs
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
ms.openlocfilehash: a44f272569741b1897caed1d1d64832d8b113eae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0003"></a>Projektbuildfehler PRJ0003  
  
> Fehler beim Erstellen des "*Befehlszeile*".  
  
Die *Befehlszeile* Befehl formatiert wird, aus der Eingabe in die **Eigenschaftenseiten** (Dialogfeld), ein Fehlercode zurückgegeben, aber keine Informationen angezeigt, der **Ausgabe** Fenster.  

Mögliche Ursachen für diesen Fehler  
  
-   Das Projekt ist abhängig von ATL-Server. Ab Visual Studio 2008, ATL-Server ist nicht mehr Bestandteil von Visual Studio, aber als shared Source-Projekt auf CodePlex freigegeben wurde. Um die ATL-Server-Quellcode und Tools herunterzuladen, wechseln Sie zu [ATL-Serverbibliothek und Tools](http://go.microsoft.com/fwlink/p/?linkid=81979).  
  
-   Geringe Systemressourcen. Schließen Sie einige Anwendungen, um dieses Problem zu beheben.  
  
-   Unzureichende Sicherheitsberechtigungen. Stellen Sie sicher, dass Sie über ausreichende Sicherheitsberechtigungen verfügen.  
  
-   Die ausführbare Datei im angegebenen Pfade **VC++-Verzeichnisse** enthalten nicht den Pfad für das Tool an, die Sie ausführen möchten. Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)  
  
-   Makefile-Projekte, werden Sie einen Befehl für die Ausführung fehlt **erstellen über die Befehlszeile** oder **neu erstellen über die Befehlszeile**.  
  
## <a name="see-also"></a>Siehe auch  
 [Projektbuildfehler und -warnungen (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)