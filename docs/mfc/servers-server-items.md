---
title: "Server: Serverelemente | Microsoft Docs"
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
  - "Architektur [C++], Serverelement"
  - "OLE-Serveranwendungen, Serverelement"
  - "Serverelement"
  - "Serverelement, Implementieren"
  - "Server [C++], Serverelement"
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Server: Serverelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn der Container einen Server startet, damit ein Benutzer ein verknüpftes oder eingebettetes OLE\-Element bearbeiten kann, erstellt die Serveranwendung ein "Serverelement." Das Serverelement, das ein Objekt einer Klasse, abgeleitet von `COleServerItem`, bietet eine Schnittstelle zwischen dem Serverdokument und der Containeranwendung.  
  
 Die `COleServerItem`\-Klasse definiert mehrere überschreibbare Memberfunktionen, die in OLE aufgerufen werden, normalerweise als Reaktion für Anforderungen vom Container.  Serverelemente können Teil des Serverdokuments oder des gesamten Dokuments darstellen.  Wenn ein OLE\-Element im Containerdokument eingebettet wird, stellt das Serverelement das gesamte Serverdokument dar.  Wenn das OLE\-Element verknüpft wird, kann das Serverelement einen Teil des Serverdokuments oder für darstellen, je nachdem, ob der Link an einen Teil oder den gesamten ist.  
  
 Im Beispiel [HIERSVR](../top/visual-cpp-samples.md) beispielsweise die ServerElementklasse, **CServerItem**, über einen Member, der ein Zeiger auf ein Objekt der Klasse **CServerNode** ist.  Das **CServerNode**\-Objekt ist ein Knoten im Dokument der HIERSVR\-Anwendung, in dem eine Struktur ist.  Wenn das Objekt **CServerNode** der Stammknoten ist, stellt das **CServerItem**\-Objekt das ganze Dokument dar.  Wenn das Objekt **CServerNode** ein untergeordneter Knoten ist, stellt das **CServerItem**\-Objekt einen Teil des Dokuments.  Siehe das Beispiel [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE ein Beispiel dieser Interaktion.  
  
##  <a name="_core_implementing_server_items"></a> Implementieren von Server\-Elementen  
 Wenn Sie im Anwendungs\-Assistenten verwenden, um "Starter" Code für die Anwendung erstellen, ist der gesamte, den Sie ausführen müssen, um Serverelemente im Startcode einzuschließen, eine der Serveroptionen von der OLE\-Optionsseite auszuwählen.  Wenn Sie Serverelementen in einer vorhandenen Anwendung hinzufügen, führen Sie die folgenden Schritte aus:  
  
#### Um ein Serverelement implementieren  
  
1.  Leiten Sie eine Klasse von `COleServerItem` ab.  
  
2.  In einer abgeleiteten Klasse überschreiben Sie die `OnDraw`\-Memberfunktion.  
  
     Das Framework ruft `OnDraw` auf, um das OLE\-Element in einer Metadatei zu rendern.  Die Containeranwendung verwendet diese Metadatei, um das Element zu rendern.  Die Ansichtsklasse der Anwendung verfügt auch `OnDraw` eine Memberfunktion, die verwendet wird, um das Element zu rendern, wenn die Serveranwendung aktiv ist.  
  
3.  Implementieren Sie eine Überschreibung von `OnGetEmbeddedItem` für die ServerDokumentklasse.  Weitere Informationen finden Sie im Artikel [Server: Implementieren von Server\-Dokumenten](../mfc/servers-implementing-server-documents.md) und das Beispiel [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE.  
  
4.  Implementieren Sie `OnGetExtent`\-Memberfunktion der ServerElementklasse.  Das Framework ruft diese Funktion auf, um die Größe des Elements abzurufen.  Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> Ein für Server\-Element\-Architektur Tipp  
 Wie in [Implementieren von Server\-Elementen](#_core_implementing_server_items) erwähnt, müssen Serveranwendungen in der Lage sein, Elemente beide in des Servers und in einer Metadatei zu rendern, die von der Containeranwendung verwendet wird.  In der Anwendungsarchitektur der Microsoft Foundation Class\-Bibliothek rendert die `OnDraw`\-Memberfunktion der Ansichtsklasse das Element, wenn sie geändert werden \(siehe [CView::OnDraw](../Topic/CView::OnDraw.md) in der Class Library Reference.\)  `OnDraw` des Serverelements rendert das Element in eine Metadatei in allen anderen Fällen \(siehe [COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)\).  
  
 Sie können Duplizierung von Code vermeiden, indem Sie Hilfsfunktionen in der ServerDokumentklasse schreiben und sie aus den `OnDraw`\-Funktionen in den ServerElementklassen Ansichts\- und aufrufen.  Das [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE verwendet diese Strategie: die Funktionen **CServerView::OnDraw** und **CServerItem::OnDraw** beide rufen **CServerDoc::DrawTree** auf, um das Element zu rendern.  
  
 Die Ansicht und das Element verfügen beide über `OnDraw`\-Memberfunktionen, da sie unter verschiedenen Bedingungen zeichnen.  Die Ansicht muss solche Faktoren wie Zoomen, Auswahlgröße und \-Wertebereich, Clipping und Benutzeroberflächenelemente wie Bildlaufleisten berücksichtigen.  Das Serverelement hingegen immer zeichnet das gesamte OLE\-Objekt.  
  
 Weitere Informationen finden Sie unter [CView::OnDraw](../Topic/CView::OnDraw.md), [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md) und [COleServerDoc::OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) in der Class Library Reference.  
  
## Siehe auch  
 [Server](../mfc/servers.md)