---
title: "Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus | Microsoft Docs"
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
  - "Anwendungen [OLE], Zwischenablage"
  - "Zwischenablage [C++], OLE-Formate"
  - "Formate [C++], Zwischenablage für OLE"
  - "OLE-Zwischenablage"
  - "OLE-Zwischenablage, Formate"
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE verwendet Standardformate und einige OLE\-Besondereformate für die Übertragung von Daten durch die Zwischenablage.  
  
 Als Sie oder Kopieren von Daten von einer Anwendung ausgeschnittene, werden die Daten auf der gespeichert in den Einfügevorgängen später verwendet werden Zwischenablage.  Diese Daten sind in einer Vielzahl von Formaten.  Wenn ein Benutzer beschließt, um Daten aus der Zwischenablage einfügen, kann die Anwendung auswählen, die von diesen Formaten zu verwenden.  Die Anwendung sollte geschrieben werden, um das Format aus, das die meisten Informationen, es sei denn, der Benutzer speziell um ein bestimmtes Format anfordert, mit einfügens Inhalte bereitstellt.  Bevor Sie fortfahren sollten Sie die Themen [Datenobjekte und Datenquellen \(OLE\)](../mfc/data-objects-and-data-sources-ole.md) lesen.  Sie beschreiben die Grundlagen, wie Datenübertragungen arbeiten und wie sie in Anwendungen implementiert.  
  
 Windows definiert einige Standardformate, die zum Übertragen von Daten von der Zwischenablage verwendet werden können.  Diese schließen Metadateien, Bitmaps, Text und andere.  OLE definiert mehrere OLE\-Besondereformate, auch.  Für Anwendungen, die weitere Details als durch diese Standardformate angegeben benötigen, empfiehlt es sich, ihre eigenen benutzerdefinierten Zwischenablageformate zu registrieren.  Verwenden Sie in der Win32 API\-Funktion [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049), um dazu.  
  
 Beispielsweise registriert Microsoft Excel ein benutzerdefiniertes Format für Arbeitsblätter.  Dieses Format enthält wesentlich mehr Informationen, als beispielsweise eine Bitmap veranschaulicht.  Wenn diese Daten in eine Anwendung eingefügt werden, die im XML\-Arbeitsblattformat für unterstützt, werden alle Formeln und Werte im Arbeitsblatt beibehalten und können bei Bedarf aktualisiert werden.  Microsoft Excel wird auch Daten in der Zwischenablage in Formatvorlagen, damit sie als OLE\-Element eingefügt werden kann.  Jeder OLE\-Dokumentcontainer kann diese Informationen als eingebettetes Element einfügen.  Dies eingebettete Element kann mit Microsoft Excel geändert werden.  Die Zwischenablage enthält ebenfalls eine einfache Bitmap des Bilds des ausgewählten Bereichs auf dem Arbeitsblatt.  Dies kann in OLE\-Dokumentcontainer oder in Bitmap\-Editoren, wie Farbe ebenfalls eingefügt werden.  Bei einer Bitmap hingegen gibt es keine Möglichkeit, die Daten als ein Arbeitsblatt bearbeiten.  
  
 Um die maximale Menge aus der Zwischenablage abzurufen, sollten Anwendungen für diese benutzerdefinierten Formaten überprüfen bevor sie Daten aus der Zwischenablage einfügen.  
  
 Um beispielsweise den Befehl Ausschneiden zu aktivieren, können z Sie Handler in etwa Folgendes:  
  
 [!CODE [NVC_MFCListView#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCListView#3)]  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)  
  
-   [Verwenden der Zwischenablage](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
-   [OLE\-Datenobjekte und Datenquellen und einheitliche Datenübertragung](../mfc/data-objects-and-data-sources-ole.md)  
  
## Siehe auch  
 [Zwischenablage](../mfc/clipboard.md)