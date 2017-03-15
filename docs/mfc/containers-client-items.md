---
title: "Container: Clientelemente | Microsoft Docs"
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
  - "Clientelemente und OLE-Container"
  - "OLE-Container, Clientelemente"
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Container: Clientelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt, was Clientelemente sind und dafür, was welche Klassen die Anwendung ihre Clientelemente ableiten soll.  
  
 Clientelemente sind die Datenelemente, die einer anderen Anwendung gehören, die entweder in enthalten oder durch das Dokument einer OLE\-Containeranwendung verwiesen.  Clientelemente, deren Daten im Dokument enthalten sind, werden eingebettet; die, deren Daten in einem anderen Speicherort gespeichert werden, der vom Containerdokument verwiesen wird, werden verknüpft.  
  
 Die Dokumentklasse in einer OLE\-Anwendung wird von der [COleDocument](../mfc/reference/coledocument-class.md) anstelle von **CDocument** abgeleitet.  Die `COleDocument`\-Klasse erbt von **CDocument** die gesamte Funktionalität, die für die Anwendung der Dokument\-\/Ansichtarchitektur erforderlich ist, der auf MFC\-Anwendungen basieren.  `COleDocument` definiert auch eine Schnittstelle, die ein Dokument als Auflistung `CDocItem`\-Objekte behandelt.  Einige `COleDocument`\-Memberfunktionen werden zum Hinzufügen, das Abrufen und das Löschen von Elementen dieser Auflistung bereitgestellt.  
  
 Jede Containeranwendung sollte eine Klasse von `COleClientItem` mindestens berechnen.  Objekte dieser Klasse stellen die Elemente, eingebettet, oder im OLE\-Dokument verknüpft.  Diese Objekte bestehen für die Lebensdauer des Dokuments, das sie enthält, es sei denn, sie aus dem Dokument gelöscht werden.  
  
 `CDocItem` ist die Basisklasse für `COleClientItem` und `COleServerItem`.  Objekte von Klassen, die von diesen zwei abgeleitet werden, dienen als Vermittler zwischen dem OLE\-Element und Client und Serveranwendungen, bzw. auf.  Jedes Mal wenn ein neues OLE\-Element dem Dokument hinzugefügt ist, fügt das MFC\-Framework einem neuen Objekt von `COleClientItem` abgeleiteten Klasse der Clientanwendung zur Auflistung des Dokuments von `CDocItem`\-Objekten hinzu.  
  
## Siehe auch  
 [Container](../mfc/containers.md)   
 [Container: Verbunddateien](../mfc/containers-compound-files.md)   
 [Container: Probleme mit der Benutzeroberfläche](../mfc/containers-user-interface-issues.md)   
 [Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md)   
 [COleClientItem Class](../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Class](../mfc/reference/coleserveritem-class.md)