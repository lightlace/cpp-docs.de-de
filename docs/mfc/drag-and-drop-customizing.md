---
title: "Drag&#160;&amp;&#160;Drop: Anpassen | Microsoft Docs"
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
  - "Drag & Drop, DoDragDrop aufrufen"
  - "Drag & Drop, COleDataSource-Objekt"
  - "Drag & Drop, Anpassen des Verhaltens"
  - "Drag & Drop, implementieren in nicht-OLE-Anwendungen"
  - "Drag & Drop (OLE), Anpassen des Verhaltens"
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Drag&#160;&amp;&#160;Drop: Anpassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Standardimplementierung der Drag & Drop\-Funktion ist für die meisten Anwendungen ausreichend.  erfordern jedoch möglicherweise einige Anwendungen, dass dieses Standardverhalten geändert wird.  Dieser Artikel beschreibt die Schritte, die erforderlich sind, diese Standardwerte zu ändern.  Außerdem können Sie diese Technik anwenden, Anwendungen eingerichtet, die Verbunddokumente nicht als Ablagequellen unterstützen.  
  
 Wenn Sie Standard\-OLE\-Drag& Drop\-Verhalten anpassen oder eine Anwendung NichtOLE haben, müssen Sie ein `COleDataSource`\-Objekt erstellen, um die Daten zu speichern.  Wenn der Benutzer einen Drag & Drop\-Operation beginnt, muss der Code die `DoDragDrop`\-Funktion von diesem Objekt anstelle anderer Klassen aufrufen, die Drag & Drop\-Vorgänge unterstützen.  
  
 Optional können Sie ein `COleDropSource`\-Objekt erstellen, um der Ablegevorgang zu steuern und einige seiner Fähigkeiten je nach Typ des Verhaltens zu überschreiben, das Sie ändern möchten.  Dies Ablagequellenobjekt wird dann an `COleDataSource::DoDragDrop` übergeben, um das Standardverhalten dieser Funktionen zu ändern.  Diese unterschiedlichen Optionen ermöglichen viel Flexibilität in, wie Sie Drag & Drop\-Operationen in der Anwendung unterstützen.  Weitere Informationen über Datenquellen, finden Sie im Artikel [Datenobjekte und Datenquellen \(OLE\)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Sie können die folgenden Funktionen überschreiben, von Drag & Drop\-Vorgängen anzupassen:  
  
|Überschreiben|So anpassen|  
|-------------------|-----------------|  
|`OnBeginDrag`|Wie wird initiiert wird, nachdem Sie `DoDragDrop` aufrufen.|  
|`GiveFeedback`|Visuelles Feedback, wie Cursor\-Darstellung, um verschiedene Ablagenergebnisse.|  
|`QueryContinueDrag`|Die Beendigung eines Drag & Drop\-Vorgangs.  Diese Funktion ermöglicht Ihnen, die Modifizierertastenzustände während des Ziehvorgangs zu überprüfen.|  
  
## Siehe auch  
 [Drag & Drop \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDropSource Class](../mfc/reference/coledropsource-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)