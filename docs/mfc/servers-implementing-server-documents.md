---
title: 'Server: Implementieren von Serverdokumenten | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c4b8618e4951ac499d504cc68b0552ea45eed03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-server-documents"></a>Server: Implementieren von Serverdokumenten
Dieser Artikel beschreibt die Schritte, die Sie ausführen müssen, um erfolgreich Serverdokument implementieren, wenn Sie nicht die OLE-Serveroption im Anwendungs-Assistenten angegeben haben.  
  
#### <a name="to-define-a-server-document-class"></a>So definieren Sie eine Server-Dokument-Klasse  
  
1.  Leiten Sie eine Dokumentklasse aus `COleServerDoc` anstelle von **CDocument**.  
  
2.  Erstellen Sie eine Server-Element-Klasse abgeleitet `COleServerItem`.  
  
3.  Implementieren der `OnGetEmbeddedItem` Memberfunktion der Klasse Dokument Server.  
  
     `OnGetEmbeddedItem`wird aufgerufen, wenn der Benutzer eine Steuerelementcontainer-Anwendung erstellt oder ein eingebettetes Element bearbeitet. Es sollte ein Element, das das gesamte Dokument darstellt, zurückgegeben. Dies muss ein Objekt des Ihrer `COleServerItem`-Klasse.  
  
4.  Überschreiben der `Serialize` Memberfunktion, um den Inhalt des Dokuments zu serialisieren. Sie müssen nicht die Liste der Elemente des Servers zu serialisieren, es sei denn, Sie sie verwenden die systemeigenen Daten in Ihrem Dokument darstellen. Weitere Informationen finden Sie unter *Serverelement implementieren* im Artikel [Server: Serverelemente](../mfc/servers-server-items.md).  
  
 Wenn ein Serverdokument erstellt wird, registriert das Framework automatisch das Dokument mit der OLE-System-DLLs. Dadurch werden die DLLs der Serverdokumente zu identifizieren.  
  
 Weitere Informationen finden Sie unter [COleServerItem](../mfc/reference/coleserveritem-class.md) und [COleServerDoc](../mfc/reference/coleserverdoc-class.md) in der *Klassenbibliotheksreferenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Server](../mfc/servers.md)   
 [Server: Serverelemente](../mfc/servers-server-items.md)   
 [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md)   
 [Server: Implementieren eines In-Place-Frame-Fensters](../mfc/servers-implementing-in-place-frame-windows.md)

