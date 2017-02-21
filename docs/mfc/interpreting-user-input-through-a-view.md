---
title: "Interpretieren der Benutzereingaben in einer Ansicht | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CView-Klasse, Interpretieren von Benutzereingabe"
  - "Eingabe, view-Klasse"
  - "Interpretieren von Benutzereingaben durch Ansichten"
  - "Benutzereingabe, Interpretieren durch view-Klasse"
  - "Ansichten, Benutzerschnittstelle und -eingabe"
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Interpretieren der Benutzereingaben in einer Ansicht
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Andere Memberfunktionen der Ansicht behandeln und interpretieren alle Benutzereingaben.  Sie definieren normalerweise Meldungshandlermemberfunktionen in der Ansichtsklasse, um zu verarbeiten:  
  
-   Windows [Meldungen](../mfc/messages.md) generiert von Maus\- und Tastaturaktionen.  
  
-   [Befehle](../mfc/user-interface-objects-and-command-ids.md) von Menüs, von Symbolleistenschaltflächen und den Tastenkombinationen.  
  
 Diese Meldungshandlermemberfunktionen interpretieren die folgenden Aktionen als Dateneingabe, Auswahl oder Bearbeitung, einschließlich sie überträgt Daten zu und von der Zwischenablage:  
  
-   Mausbewegungen und \-Klicke, Ziehen und doppelklicken  
  
-   Tastatureingaben  
  
-   Menübefehle  
  
 Welche Windows\-Meldungen die Ansicht bearbeitet, hängt von den Anforderungen der Anwendung ab.  
  
 [Nachrichtenverarbeitungs\- und Zuordnungs\-Themen](../mfc/message-handling-and-mapping.md) erläutert, wie Menüelemente und andere Benutzeroberflächen\-Objekte auf Befehle zuweist und wie die Befehle in Handlerfunktionen bindet.  [Nachrichtenverarbeitungs\- und Zuordnungs\-Themen](../mfc/message-handling-and-mapping.md) wird auch beschrieben, wie MFC Befehle weiterleitet und Standardwindows\-meldungen auf Objekte sendet, die Handler für diese enthalten.  
  
 So muss die Anwendung direkte Mauszeichnung in der Ansicht implementieren.  Das Scribble\-Beispiel zeigt, wie `WM_LBUTTONDOWN`, `WM_MOUSEMOVE` und `WM_LBUTTONUP` bzw. Meldungen behandelt, der die Zeichnung eines Liniensegments zu beginnen, Fortsetzen und Beenden.  Umgekehrt müssen Sie in einigen Fällen einen Mausklick in der Ansicht als Auswahl interpretieren.  `OnLButtonDown`\-Handlerfunktion der Ansicht kann bestimmen, ob der Benutzer Sie aufgezeichnete oder auswählte.  Beim Auswählen, würde der Handler bestimmen, ob der Klick innerhalb der Grenzen einige Objekts in der Ansicht und wenn ja war, die Anzeige, um das Objekt anzuzeigen ändert, z ausgewählt.  
  
 Die Ansicht könnte beispielsweise außerdem spezifische Menübefehle, z die im Menü Bearbeiten die Vorgänge Ausschneiden, kopieren, einfügen oder löschen ausgewählte Daten mithilfe der Zwischenablage.  Ein solches Handler würde mehrere der Zwischenablage\-verknüpften Memberfunktionen der `CWnd`\-Klasse aufrufen, um ein ausgewähltes Datenelement in oder aus der Zwischenablage zu übertragen.  
  
## Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)