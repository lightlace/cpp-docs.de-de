---
title: "Output (Ger&#228;tekontext)-Klassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.classes.output"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gerätekontexte, Klassen"
  - "Ausgabeklassen"
  - "Druckklassen"
  - "Druckklassen"
  - "Bildschirmausgabeklassen"
  - "Fensterzeichnungsklassen"
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Output (Ger&#228;tekontext)-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen kapseln die verschiedenen Gerätekontexten, die in Windows verfügbar sind.  
  
 Die meisten folgenden Klassen kapseln ein Handle zu einem Windows\-Gerätekontext.  Ein Gerätekontext ist ein Windows\-Objekt, das Informationen über die Zeichnungsattribute eines Geräts wie eine Anzeige oder Drucker enthält.  Alle Zeichnungsaufrufe werden durch ein Gerätekontextobjekt gemacht.  Zusätzliche Klassen, die von `CDC` abgeleitet werden, kapseln spezialisierte Gerätekontextfunktionalität, einschließlich der Unterstützung für Windows\-Metadateien.  
  
 [CDC](../mfc/reference/cdc-class.md)  
 Die Basisklasse für Gerätekontexte.  Wird direkt für den Zugriff auf die Ganzanzeige und für den Zugriff auf nondisplay Kontexte wie Drucker.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md)  
 Ein Anzeigekontext verwendet in `OnPaint`\-Memberfunktionen von Fenstern.  Ruft `BeginPaint` automatisch auf Erstellen und `EndPaint` auf Zerstörung auf.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md)  
 Ein Clientbereiche Anzeigekontext für Fenster.  Wird beispielsweise in einer unmittelbaren Antwort zu Mausereignissen zeichnen.  
  
 [CWindowDC](../mfc/reference/cwindowdc-class.md)  
 Ein Anzeigekontext für gesamten Fenster, einschließlich den Client\- als auch Nicht\-Client\-Bereiche.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md)  
 Ein Gerätekontext für Windows\-Metadateien.  Eine Windows\-Metadatei enthält eine Sequenz von Graphics Device Interface \(GDI\)\- Befehlen, die wiedergegeben werden können, ein Bild zu erstellen.  Die Aufrufe, die den Memberfunktionen von `CMetaFileDC` ausgeführt werden, werden in einer Metadatei aufgezeichnet.  
  
## Verwandte Klassen  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Threads koordinieren \(x, y\) von Paaren.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Threads überholen, oder relativen Positionen bei zugeordneten Werte.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Griffkoordinaten rechteckigen von Bereichen.  
  
 [CRgn](../mfc/reference/crgn-class.md)  
 Kapselt einen GDI\-Bereich zum Bearbeiten eines elliptischen, oder polygonalen unregelmäßigen Bereichs innerhalb eines Fensters.  Wird in Verbindung mit den Clippingmemberfunktionen in der Klasse `CDC`.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Anzeigen und Handles die Benutzeroberfläche zum Ändern und Verschieben von rechteckigen Objekten.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Stellt ein Standarddialogfeld zum Auswählen einer Farbe zur Verfügung.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Stellt ein Standarddialogfeld für das Auswählen einer Schriftart zur Verfügung.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Stellt ein Standarddialogfeld zum Drucken einer Datei.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)