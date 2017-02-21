---
title: "CDocItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocItem class"
  - "client document items"
  - "container document items"
  - "document items"
  - "items, Dokument"
  - "OLE-Dokumente, items"
  - "server documents"
  - "server documents, document items"
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CDocItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für Dokumentelemente, die Komponenten der Daten eines Dokuments sind.  
  
## Syntax  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDocItem::GetDocument](../Topic/CDocItem::GetDocument.md)|Gibt das Dokument zurück, das das Element enthält.|  
|[CDocItem::IsBlank](../Topic/CDocItem::IsBlank.md)|Bestimmt, ob das Element alle Informationen enthält.|  
  
## Hinweise  
 `CDocItem`\-Objekte werden verwendet, um OLE\-Elemente in Client\- als auch Serverdokumenten darzustellen.  
  
 Weitere Informationen finden Sie im Artikel [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)