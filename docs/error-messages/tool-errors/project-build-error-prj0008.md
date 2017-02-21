---
title: "Projektbuildfehler PRJ0008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0008"
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Projektbuildfehler PRJ0008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Datei "Datei" konnte nicht gelöscht werden.  
  
 **Stellen Sie sicher, dass die Datei nicht durch einen anderen Prozess geöffnet und nicht schreibgeschützt ist.**  
  
 Während eines Rebuilds oder einer Bereinigung löscht Visual C\+\+ alle bekannten Zwischen\- und Ausgabedateien für das Build sowie alle Dateien, die die Platzhalterkriterien in der Eigenschaft **Zu löschende Erweiterungen während des Reinigens** auf der [Eigenschaftenseite "Allgemein" \(Projekt\)](../../ide/general-property-page-project.md) erfüllen.  
  
 Dieser Fehler wird ausgegeben, wenn Visual C\+\+ nicht in der Lage ist, eine Datei zu löschen.  Damit der Fehler behoben wird, müssen die Datei und ihr Verzeichnis vom Benutzer, der das Build erstellt, überschrieben werden können.