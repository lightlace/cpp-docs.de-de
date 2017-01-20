---
title: "Projektbuildfehler PRJ0006"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0006"
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die temporäre Datei "Datei" konnte nicht geöffnet werden.Stellen Sie sicher, dass die Datei vorhanden ist und dass das Verzeichnis nicht schreibgeschützt ist.  
  
 Visual C\+\+ konnte während des Buildprozesses keine temporäre Datei erstellen.  Folgende Gründe können vorliegen:  
  
-   Es ist kein temporäres Verzeichnis vorhanden.  
  
-   Das temporäre Verzeichnis ist schreibgeschützt.  
  
-   Es ist nicht genügend Festplattenspeicher verfügbar.  
  
-   Der Ordner **$\(IntDir\)** ist entweder schreibgeschützt oder enthält temporäre Dateien, die schreibgeschützt sind.  
  
 Dieser Fehler tritt auch im Anschluss an Fehler PRJ0007 auf: Das Ausgabeverzeichnis "*Verzeichnis*" konnte nicht erstellt werden.  Fehler PRJ0007 weist darauf hin, dass das Verzeichnis **$\(IntDir\)** nicht erstellt werden konnte, woraus folgt, dass auch keine temporären Dateien erstellt werden konnten.  
  
 Temporäre Dateien werden erstellt, wenn Sie Folgendes festlegen:  
  
-   Eine Antwortdatei  
  
-   Ein benutzerdefinierter Buildschritt  
  
-   Ein Buildereignis