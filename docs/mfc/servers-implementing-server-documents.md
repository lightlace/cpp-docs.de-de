---
title: "Server: Implementieren von Serverdokumenten"
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
  - "OLE-Serveranwendungen, Implementieren von OLE-Servern"
  - "OLE-Serveranwendungen, Verwalten von Serverdokumenten"
  - "Serverdokumente, Implementieren"
  - "Server, Serverdokumente"
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Server: Implementieren von Serverdokumenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Schritte, die Sie ausführen, um ein Serverdokument erfolgreich implementieren, wenn Sie nicht der OLE\-Serveroption im Anwendungs\-Assistenten angegeben haben.  
  
#### Um eine Serverdokumentklasse definieren  
  
1.  Leiten Sie die Dokumentklasse von `COleServerDoc` anstelle von **CDocument**.  
  
2.  Erstellen Sie eine Serverelementklasse, die von `COleServerItem` abgeleitet wird.  
  
3.  Implementieren Sie die `OnGetEmbeddedItem`\-Memberfunktion der Serverdokumentklasse.  
  
     `OnGetEmbeddedItem` wird aufgerufen, wenn der Benutzer eine Containeranwendung ein eingebettetes Element erstellt oder bearbeitet.  Es sollte ein Element zurück, das das gesamte Dokument darstellt.  Dies sollte ein Objekt der von `COleServerItem` abgeleitete Klasse sein.  
  
4.  Überschreiben Sie die `Serialize`\-Memberfunktion, um den Inhalt des Dokuments zu serialisieren.  Sie müssen nicht, um die Liste der Serverelementen zu serialisieren, es sei denn, Sie sie verwenden, um die systemeigene Daten im Dokument.  Weitere Informationen finden Sie unter *das Implementieren von Server\-Elementen* im Artikel [Server: Serverelemente](../mfc/servers-server-items.md).  
  
 Wenn ein Serverdokument erstellt wird, registriert das Framework automatisch das Dokument mit den OLE\-System\-DLLs.  Dadurch können die DLLs, die Serverdokumente zu identifizieren.  
  
 Weitere Informationen finden Sie unter [COleServerItem](../mfc/reference/coleserveritem-class.md) und [COleServerDoc](../mfc/reference/coleserverdoc-class.md) in der Class Library Reference.  
  
## Siehe auch  
 [Server](../mfc/servers.md)   
 [Server: Serverelemente](../mfc/servers-server-items.md)   
 [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)   
 [Server: Implementieren eines In\-Place\-Frame\-Fensters](../mfc/servers-implementing-in-place-frame-windows.md)