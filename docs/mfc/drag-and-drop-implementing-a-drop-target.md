---
title: "Drag&#160;&amp;&#160;Drop: Implementieren eines Drag&#160;&amp;&#160;Drop-Ziels | Microsoft Docs"
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
  - "Drag & Drop, Ablageziel"
  - "Drag & Drop (OLE), Ablageziel"
  - "Drag & Drop (OLE), Ablageziele implementieren"
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Drag&#160;&amp;&#160;Drop: Implementieren eines Drag&#160;&amp;&#160;Drop-Ziels
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Konturen dieses Artikels, wie die Anwendung ein Ablageziel.  Das Implementieren eines Ablageziels akzeptiert etwas mehr Arbeit als, eine Ablagequelle implementiert, jedoch immer noch relativ einfach.  Diese Methoden gelten auch auf Anwendungen NichtOLE zu.  
  
#### So ein Ablageziel implementieren  
  
1.  Fügen Sie eine Membervariable jeder Ansicht in der Anwendung hinzu, dass Sie ein Ablageziel sein möchten.  Diese Membervariable muss vom Typ `COleDropTarget` oder von einer Klasse sein, die davon abgeleitet wird.  
  
2.  Von der Funktion der Ansichtsklasse, die die Meldung verarbeitet `WM_CREATE` \(normalerweise `OnCreate`\), rufen Sie die neue `Register`\-Memberfunktion der Membervariable auf.  `Revoke` wird automatisch für Sie aufgerufen, wenn die Ansicht zerstört wird.  
  
3.  Überschreiben Sie die folgenden Funktionen.  Wenn Sie dasselbe Verhalten während Ihrer Anwendung soll, überschreiben Sie diese Funktionen in der Ansichtsklasse.  Wenn Sie Verhalten in Einzelfällen ändern oder das Ablegen auf Nicht\-`CView` Fenster aktivieren möchten, überschreiben Sie diese Funktionen in der von `COleDropTarget` abgeleiteten Klasse.  
  
    |Überschreiben|So unterstützen|  
    |-------------------|---------------------|  
    |`OnDragEnter`|Drop\-Vorgänge, die im Fenster ein.  Wird aufgerufen, wenn der Cursor zunächst im Fenster.|  
    |`OnDragLeave`|Spezielles Verhalten, wenn der Ziehvorgang das angegebene Fenster bleibt.|  
    |`OnDragOver`|Drop\-Vorgänge, die im Fenster ein.  Wird aufgerufen, wenn der Cursor zum Fenster gezogen wird.|  
    |`OnDrop`|Behandlung der Daten, die im angegebenen Fenster abgelegt werden.|  
    |`OnScrollBy`|Spezielles Verhalten für, ob Scrollen im Zielfenster erforderlich ist.|  
  
 Siehe die MAINVIEW.CPP\-Datei, die Teil des Beispiels [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE als ein Beispiel dafür handelt, wie diese zusammenarbeiten Funktionen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Implementieren einer Quelle](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [OLE\-Datenobjekte und \-Datenquellen Erstellen und Löschen eines Auflistungsobjekts](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Bearbeiten von OLE\-Datenobjekten und \-Datenquellen](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## Siehe auch  
 [Drag & Drop \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDropTarget Class](../mfc/reference/coledroptarget-class.md)