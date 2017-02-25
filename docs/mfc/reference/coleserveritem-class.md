---
title: "COleServerItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleServerItem class"
  - "OLE-Serveranwendungen, managing server documents"
  - "OLE-Serveranwendungen, server interfaces"
  - "OLE server documents"
  - "Server, OLE"
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleServerItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Serverschnittstelle zu den OLE\-Elementen bereit.  
  
## Syntax  
  
```  
class COleServerItem : public CDocItem  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](../Topic/COleServerItem::COleServerItem.md)|Erstellt ein `COleServerItem`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](../Topic/COleServerItem::AddOtherClipboardData.md)|Platzpräsentations\- und \-Konvertierungsformate in `COleDataSource` ein Objekt.|  
|[COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md)|Kopiert das Element in die Zwischenablage.|  
|[COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md)|Führt ein Drag & Drop\-Vorgang aus.|  
|[COleServerItem::GetClipboardData](../Topic/COleServerItem::GetClipboardData.md)|Ruft die Datenquelle zur Verwendung in der Datenübertragung ab \(Drag & Drop oder Zwischenablage\).|  
|[COleServerItem::GetDocument](../Topic/COleServerItem::GetDocument.md)|Gibt das Serverdokument zurück, das das Element enthält.|  
|[COleServerItem::GetEmbedSourceData](../Topic/COleServerItem::GetEmbedSourceData.md)|Ruft die **CF\_EMBEDSOURCE** Daten für ein OLE\-Element ab.|  
|[COleServerItem::GetItemName](../Topic/COleServerItem::GetItemName.md)|Gibt den Namen des Elements zurück.  Wird nur für verknüpfte Elemente.|  
|[COleServerItem::GetLinkSourceData](../Topic/COleServerItem::GetLinkSourceData.md)|Ruft die `CF_LINKSOURCE` Daten für ein OLE\-Element ab.|  
|[COleServerItem::GetObjectDescriptorData](../Topic/COleServerItem::GetObjectDescriptorData.md)|Ruft die **CF\_OBJECTDESCRIPTOR** Daten für ein OLE\-Element ab.|  
|[COleServerItem::IsConnected](../Topic/COleServerItem::IsConnected.md)|Gibt an, ob das Element derzeit einem aktiven Container angefügt wird.|  
|[COleServerItem::IsLinkedItem](../Topic/COleServerItem::IsLinkedItem.md)|Gibt an, ob das Element ein verknüpftes OLE\-Element darstellt.|  
|[COleServerItem::NotifyChanged](../Topic/COleServerItem::NotifyChanged.md)|Aktualisiert alle Container mit Update der automatischen Verknüpfung.|  
|[COleServerItem::OnDoVerb](../Topic/COleServerItem::OnDoVerb.md)|Aufgerufen, um ein Verb auszuführen.|  
|[COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)|Aufgerufen wenn die Containeranforderungen, das Element zu zeichnen, Implementierung erforderlich.|  
|[COleServerItem::OnDrawEx](../Topic/COleServerItem::OnDrawEx.md)|Aufgerufen für spezielle Elementzeichnung.|  
|[COleServerItem::OnGetClipboardData](../Topic/COleServerItem::OnGetClipboardData.md)|Aufgerufen vom Framework, um die Daten abzurufen, die in die Zwischenablage kopiert werden.|  
|[COleServerItem::OnGetExtent](../Topic/COleServerItem::OnGetExtent.md)|Aufgerufen vom Framework, um die Größe des OLE\-Elements abzurufen.|  
|[COleServerItem::OnInitFromData](../Topic/COleServerItem::OnInitFromData.md)|Aufgerufen durch das Framework, um ein OLE\-Element mit den Inhalt des Datenübertragungsobjekts zu initialisieren angegeben.|  
|[COleServerItem::OnQueryUpdateItems](../Topic/COleServerItem::OnQueryUpdateItems.md)|Aufgerufen, um zu bestimmen, ob verknüpften Elemente Aktualisieren erfordern.|  
|[COleServerItem::OnRenderData](../Topic/COleServerItem::OnRenderData.md)|Ruft Daten als Teil des verzögerten Renderings ab.|  
|[COleServerItem::OnRenderFileData](../Topic/COleServerItem::OnRenderFileData.md)|Ruft Daten in ein Objekt `CFile` als Teil des verzögerten Renderings ab.|  
|[COleServerItem::OnRenderGlobalData](../Topic/COleServerItem::OnRenderGlobalData.md)|Ruft Daten in `HGLOBAL` als Teil des verzögerten Renderings ab.|  
|[COleServerItem::OnSetColorScheme](../Topic/COleServerItem::OnSetColorScheme.md)|Aufgerufen, um das Farbschema des Elements festlegen.|  
|[COleServerItem::OnSetData](../Topic/COleServerItem::OnSetData.md)|Aufgerufen, um die Daten des Elements festlegen.|  
|[COleServerItem::OnSetExtent](../Topic/COleServerItem::OnSetExtent.md)|Aufgerufen vom Framework, um die Größe des OLE\-Elements festzulegen.|  
|[COleServerItem::OnUpdate](../Topic/COleServerItem::OnUpdate.md)|Aufgerufen, wenn ein Bestandteil des Dokuments in das Element gehört, wird geändert.|  
|[COleServerItem::OnUpdateItems](../Topic/COleServerItem::OnUpdateItems.md)|Aufgerufen, um den Präsentationscachen aller Elemente im Serverdokument zu aktualisieren.|  
|[COleServerItem::SetItemName](../Topic/COleServerItem::SetItemName.md)|Legt den Namen des Elements fest.  Wird nur für verknüpfte Elemente.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleServerItem::GetDataSource](../Topic/COleServerItem::GetDataSource.md)|Ruft das Objekt ab, das den Speicherkonvertierungsformaten verwendet wird.|  
|[COleServerItem::OnHide](../Topic/COleServerItem::OnHide.md)|Aufgerufen vom Framework, um das OLE\-Element auszublenden.|  
|[COleServerItem::OnOpen](../Topic/COleServerItem::OnOpen.md)|Aufgerufen vom Framework, um das OLE\-Element in einem eigenen Fenster der obersten Ebene anzuzeigen.|  
|[COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md)|Aufgerufen wenn die Containeranforderungen, um das Element anzuzeigen.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleServerItem::m\_sizeExtent](../Topic/COleServerItem::m_sizeExtent.md)|Informiert den Server über, wie viel des OLE\-Elements sichtbar ist.|  
  
## Hinweise  
 Ein verknüpftes Element kann einige oder alle Serverdokument darstellen.  Ein eingebettetes Element stellt immer ein ganzes Serverdokument dar.  
  
 Die `COleServerItem`\-Klasse definiert mehrere überschreibbare Memberfunktionen, die von der OLE\-Systemdynamic Dynamic Link Libraries \(DLL\) aufgerufen werden, normalerweise als Reaktion auf Anforderungen von der Containeranwendung.  Diese Memberfunktionen ermöglichen die Containeranwendung, das Element auf verschiedene Arten, wie, indem es anzeigen ausführen, die Verben, oder seine Daten indirekt bearbeiten in verschiedenen Formaten abrufen.  
  
 Um `COleServerItem` zu verwenden, leiten Sie eine Klasse davon und implementieren Sie die [OnDraw](../Topic/COleServerItem::OnDraw.md) und [Serialisieren Sie](../Topic/CObject::Serialize.md)\-Memberfunktionen.  Die `OnDraw`\-Funktion bietet die Metadateidarstellung eines Elements und ermöglicht angezeigt werden können, wenn eine Containeranwendung ein Verbunddokument öffnet.  Die `Serialize`\-Funktion von `CObject` stellt die systemeigene Darstellung eines Elements und ermöglicht ein eingebettetes zwischen den Server und die Containeranwendungen zu übertragenden Element.  [OnGetExtent](../Topic/COleServerItem::OnGetExtent.md) stellt die natürliche Größe des Elements auf den Container und aktiviert den Container, um das Element zu skalieren.  
  
 Weitere Informationen zum Server und verwandte Themen, finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md) und "Erstellen einer Container\/Server\-Anwendung" im Artikel [Container: Erweiterte Funktionen](../../mfc/containers-advanced-features.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC Sampling HIERSVR](../../top/visual-cpp-samples.md)   
 [CDocItem Class](../../mfc/reference/cdocitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)