---
title: "Projektbuildfehler PRJ0009"
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
  - "PRJ0009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0009"
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In das Buildprotokoll konnte nicht geschrieben werden.  
  
 **Stellen Sie sicher, dass die Datei nicht durch einen anderen Prozess geöffnet und nicht schreibgeschützt ist.**  
  
 Nachdem Sie die Eigenschaft **Buildprotokollierung** auf **Ja** gesetzt und ein Build oder ein Rebuild erstellt haben, konnte das Buildprotokoll von Visual C\+\+ nicht im exklusiven Modus geöffnet werden.  
  
 Überprüfen Sie die Einstellung **Buildprotokollierung**, indem Sie das Dialogfeld **Optionen** öffnen \(klicken Sie im Menü **Extras** auf den Befehl **Optionen**\) und dann im Ordner **Projekte** die Option **VC\+\+\-Build** auswählen.  Die Builddatei hat die Bezeichnung **BuildLog.htm** und wird in das Zwischenverzeichnis **$\(IntDir\)** geschrieben.  
  
 Folgende Gründe können für diesen Fehler vorliegen:  
  
-   Sie führen zwei Visual C\+\+\-Prozesse parallel aus und versuchen, in beiden Prozessen eine identische Konfiguration desselben Projekts gleichzeitig zu erstellen.  
  
-   Die Buildprotokolldatei wird in einem Prozess geöffnet, durch den die Datei gesperrt ist.  
  
-   Der Benutzer hat keine Berechtigung zum Erstellen einer Datei.  
  
-   Der aktuelle Benutzer hat keinen Schreibzugriff auf die Datei **BuildLog.htm**.