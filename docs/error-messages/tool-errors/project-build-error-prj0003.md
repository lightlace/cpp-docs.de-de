---
title: "Projektbuildfehler PRJ0003"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0003"
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler beim Starten von "Befehlszeile".  
  
 Ein Befehl, ***Befehlszeile***, der aus einer Eingabe im Dialogfeld **Eigenschaftenseiten** resultiert, hat einen Fehlercode zurückgegeben, das Ausgabefenster enthält jedoch keine diesbezüglichen Informationen.  
  
 Folgende Gründe können für diesen Fehler vorliegen:  
  
-   Das Projekt hängt von ATL\-Server ab.  Ab [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] ist ATL\-Server nicht mehr Teil von Visual Studio, sondern wurde unter CodePlex als Shared\-Source\-Projekt veröffentlicht.  Um den ATL\-Server\-Quellcode und die Tools herunterzuladen, wechseln Sie zu [http:\/\/go.microsoft.com\/fwlink\/?LinkID\=81979](http://go.microsoft.com/fwlink/?LinkID=81979).  
  
-   Unzureichende Systemressourcen.  Schließen Sie einige Anwendungen, um diesen Fehler zu beheben.  
  
-   Unzureichende Sicherheitsberechtigungen.  Stellen Sie sicher, dass Sie über ausreichende Sicherheitsberechtigungen verfügen.  
  
-   Der Pfad für das auszuführende Tool ist nicht in den unter [VC\+\+\-Verzeichnisse](assetId:///e027448b-c811-4c3d-8531-4325ad3f6e02) angegebenen Pfaden für ausführbare Dateien enthalten.  
  
-   Im Fall von Makefile\-Projekten fehlt ein Befehl für die Ausführung mit **Buildbefehlszeile** oder **Neu erstellte Befehlszeile**.  
  
## Siehe auch  
 [Projektbuildfehler und \-warnungen \(PRJxxxx\)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)