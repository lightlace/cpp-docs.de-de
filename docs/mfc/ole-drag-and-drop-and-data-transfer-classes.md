---
title: "OLE-Drag &amp;-Drop und Datentransferklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Klassen [C++]"
  - "Datenübertragung [C++], OLE"
  - "Datenübertragungsklassen [C++]"
  - "Drag & Drop [C++], Klassen"
  - "Drag & Drop (OLE) [C++], und Datenübertragungsklassen"
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE-Drag &amp;-Drop und Datentransferklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen werden in OLE\-Datenübertragungen verwendet.  Sie ermöglichen die zwischen Anwendungen zu übertragenden Daten, indem die Zwischenablage oder durch Drag & Drop verwenden.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Steuert den Drag & Drop\-Vorgang vom Start zum Ende.  Diese Klasse bestimmt wenn die Ziehvorgangsanfänge und wann diese abgeschlossen.  Sie wird auch Cursor\-Feedback während des Drag & Drop\-Vorgangs an.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Wird verwendet, wenn Anwendungen Daten eine für Datenübertragung bereitstellt.  `COleDataSource` kann als Zwischenablageobjekt objektorientiertes angezeigt werden.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Stellt das Ziel eines Drag & Drop\-Vorgangs dar.  Ein `COleDropTarget`\-Objekt entspricht einem Fenster auf dem Bildschirm.  Er ermittelt, ob alle Daten akzeptiert, die darauf abgelegt werden und implementiert den tatsächlichen Drop\-Vorgang.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Wird als der Empfängerseite zu `COleDataSource`.  `COleDataObject`\-Objekte ermöglichen den Zugriff auf Daten, die durch ein `COleDataSource`\-Objekt gespeichert werden.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)