---
title: "Verwalten von Men&#252;s, Steuerleisten und Zugriffstasten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffstastentabellen [C++]"
  - "Steuerleisten, Aktualisieren in Rahmenfenstern"
  - "Rahmenfenster, Aktualisieren"
  - "MDI, Rahmenfenster"
  - "Menüs, Aktualisieren bei Kontextänderungen"
  - "Freigeben von Menüs"
  - "Statusleisten, Aktualisieren"
  - "Aktualisieren von Benutzeroberflächenobjekten"
  - "Benutzerschnittstellenobjekte, Aktualisieren"
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Verwalten von Men&#252;s, Steuerleisten und Zugriffstasten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Rahmenfenster verwaltet Aktualisieren von Benutzeroberflächenobjekten, einschließlich Menüs, Symbolleisten\-Schaltflächen, die Statusleiste und die Tastenkombinationen.  Außerdem verwaltet sie Freigeben der Menüleiste in MDI\-Anwendungen.  
  
## Verwalten von Menüs  
 Das Rahmenfenster akzeptiert beteiligt, an, Benutzeroberflächeelemente mithilfe des `ON_UPDATE_COMMAND_UI` Mechanismus zu aktualisieren, der unter [Erstellen Benutzeroberfläche\-Objekte aktualisiert](../mfc/how-to-update-user-interface-objects.md) beschrieben wird.  Schaltflächen in Symbolleisten und anderen Steuerleisten werden während der Leerlaufschleife aktualisiert.  Menüelemente in den Dropdownmenüs auf der Menüleiste werden kurz vor dem Menü ablegt unten aktualisiert.  
  
 Für MDI\-Anwendungen verwaltet das MDI\-Rahmenfenster die Menüleiste und die Beschriftung.  Ein MDI\-Rahmenfenster besitzt ein Standardmenü, das als die Menüleiste verwendet wird, wenn keine aktiven untergeordneten MDI\-Fenster gibt.  Wenn es aktive untergeordnete Elemente enthält, wird die Menüleiste des MDI\-Rahmenfensters vom Menü für das aktive untergeordnete MDI\-Fenster angewendet.  Wenn eine MDI\-Anwendung mehrere Dokumenttypen, z Diagramm\- und Arbeitsblattdokumente, jeder Typ ablegt eigene Menüs in der Menüleiste und ändert die Beschriftung des Hauptrahmenfensters unterstützt.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) stellt Standardimplementierungen für die Standardbefehle im Menü Fenster bereit, das für MDI\-Anwendungen wird.  Insbesondere wird der Befehl des neuen Fensters \(**ID\_WINDOW\_NEW**\), ein neues Rahmenfenster und eine Ansicht auf das aktuelle Dokument zu erstellen implementiert.  Sie müssen diese Implementierungen überschreiben, wenn Sie erweiterte Anpassung benötigen.  
  
 Mehrere untergeordnete MDI\-Fenster desselben Dokumenttyps geben Menüressourcen frei.  Wenn mehrere untergeordnete MDI\-Fenster durch dieselbe Normal\-Vorlage erstellt werden, können sie verwenden alle dieselbe Menüressource und speichern auf Systemressourcen in Windows.  
  
## Verwalten der Statusleiste  
 Das auch Rahmenfenster wird die Statusleiste innerhalb des Clientbereichs und verwaltet die Indikatoren der Statusleiste.  Das Rahmenfenster gelöscht und aktualisiert den Nachrichtenbereich in der Statusleiste ggf. und in den Anzeigeneingabeaufforderungs\-zeichenfolgen, während der Benutzer Menüelemente oder Symbolleisten\-Schaltflächen auswählt, wie in [Erstellen Befehls\-Informationen in der Statusleiste anzeigt](../mfc/how-to-display-command-information-in-the-status-bar.md) beschrieben.  
  
## Verwalten von Zugriffstasten  
 Jedes Rahmenfenster wartet eine optionale Zugriffstastentabelle, die Zugriffstastenübersetzung automatisch ausführt.  Dieser Mechanismus ist es einfach, die Zugriffstasten definieren \(bezeichnet als Tastenkombinationen\) Menübefehle dieses Aufrufs.  
  
## Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)