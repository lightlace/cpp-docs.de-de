---
title: "CDocObjectServerItem Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CDocObjectServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "CDocObjectServerItem class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CDocObjectServerItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Serververben implementiert der OLE speziell für DocObject\-Server.  
  
## Syntax  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](../Topic/CDocObjectServerItem::CDocObjectServerItem.md)|Erstellt ein `CDocObjectServerItem`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](../Topic/CDocObjectServerItem::GetDocument.md)|Ruft einen Zeiger auf das Dokument ab, das das Element enthält.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](../Topic/CDocObjectServerItem::OnHide.md)|Löst eine Ausnahme aus, wenn das Framework versucht, ein DocObject\-Element auszublenden.|  
|[CDocObjectServerItem::OnShow](../Topic/CDocObjectServerItem::OnShow.md)|Aufgerufen vom Framework, um das DocObject\-Element direkt aktiviert auszuführen.  Wenn das Element kein DocObject ist, ruft [COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md) auf.|  
  
## Hinweise  
 `CDocObjectServerItem` definiert überschreibbare Memberfunktionen: [OnHide](../Topic/CDocObjectServerItem::OnHide.md), [OnOpen](assetId:///7a9b1363-6ad8-4732-9959-4e35c07644fd) und [OnShow](../Topic/CDocObjectServerItem::OnShow.md).  
  
 Um `CDocObjectServerItem` zu verwenden, gewährleisten Sie die [OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) Überschreibung im `COleServerDoc` von abgeleitete Klasse gibt ein neues Objekt `CDocObjectServerItem` zurück.  Wenn Sie alle Funktionen im Element ändern müssen, können Sie eine neue Instanz von Ihrem eigenen `CDocObjectServerItem` von abgeleitete Klasse erstellen.  
  
 Weitere Informationen zu DocObjects finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in der *MFC\-Referenz*.  Siehe auch [Internet\-erste Schritte: Active Documents](../../mfc/active-documents-on-the-internet.md) und [Active Documents](../../mfc/active-documents-on-the-internet.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## Anforderungen  
 **Header:**  afxdocob.h  
  
## Siehe auch  
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer Class](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem Class](../../mfc/reference/coledocobjectitem-class.md)