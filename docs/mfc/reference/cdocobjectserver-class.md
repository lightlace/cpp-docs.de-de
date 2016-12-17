---
title: "CDocObjectServer Class"
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
  - "CDocObjectServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "CDocObjectServer class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CDocObjectServer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die zusätzlichen OLE\-Schnittstellen, die erforderlich sind, um einen normalen `COleDocument` Server in einen vollständigen DocObject\-Server zu erstellen: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget` und `IPrint`.  
  
## Syntax  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDocObjectServer::CDocObjectServer](../Topic/CDocObjectServer::CDocObjectServer.md)|Erstellt ein `CDocObjectServer`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDocObjectServer::ActivateDocObject](../Topic/CDocObjectServer::ActivateDocObject.md)|Ermöglicht den Dokumentobjektserver, zeigt aber ihn nicht an.|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDocObjectServer::OnActivateView](../Topic/CDocObjectServer::OnActivateView.md)|Zeigt die DocObject\-Ansicht an.|  
|[CDocObjectServer::OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md)|Stellt den Zustand der DocObject\-Ansicht wiederher.|  
|[CDocObjectServer::OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md)|Rettet den Zustand der DocObject\-Ansicht.|  
  
## Hinweise  
 `CDocObjectServer` wird von `CCmdTarget` und von den Arbeiten eng mit `COleServerDoc` berechnet, um die Schnittstellen verfügbar zu machen.  
  
 Ein DocObject\-Serverdokument kann [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)\-Objekte enthalten, die die Serverschnittstelle zu DocObject\-Elementen darstellen.  
  
 Um den DocObject\-Server anzupassen, eine eigene Klasse von `CDocObjectServer` zu berechnen und ihre Ansicht zu überschreiben installieren Sie Funktionen, [OnActivateView](../Topic/CDocObjectServer::OnActivateView.md), [OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md) und [OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md).  Sie müssen eine neue Instanz der Klasse als Reaktion auf Framework bereitstellen.  
  
 Weitere Informationen zu DocObjects finden Sie unter [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in der *MFC\-Referenz*.  Siehe auch [Internet\-erste Schritte: Active Documents](../../mfc/active-documents-on-the-internet.md) und [Active Documents](../../mfc/active-documents-on-the-internet.md).  
  
 Siehe auch im folgenden Knowledge Base\-Artikel:  
  
-   Q247382: PRB: QuickInfos für Steuerelemente im ActiveX\-Dokumenten\-Server werden durch den ActiveX\-Dokumenten\-Container ausgeblendet  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## Anforderungen  
 **Header:** afxdocob.h  
  
## Siehe auch  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem Class](../../mfc/reference/cdocobjectserveritem-class.md)