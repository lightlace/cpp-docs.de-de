---
title: "COleDataSource Class"
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
  - "COleDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zwischenablage [C++], MFC-Unterstützung"
  - "Zwischenablage [C++], OLE-Unterstützung"
  - "COleDataSource class"
  - "data transfer [C++], OLE"
  - "drag and drop [C++], MFC-Unterstützung"
  - "IDataObject, MFC encapsulation"
  - "OLE [C++], uniform data transfer"
  - "OLE Clipboard [C++], Unterstützung"
  - "OLE data transfer [C++]"
  - "uniform data transfer"
  - "uniform data transfer, OLE"
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# COleDataSource Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fungiert als Cache auf, in der eine Anwendung die Daten platziert, die sie während der Datenübertragungsvorgänge, wie Zwischenablage oder Drag & Drop\-Operationen bietet.  
  
## Syntax  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](../Topic/COleDataSource::COleDataSource.md)|Erstellt ein `COleDataSource`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDataSource::CacheData](../Topic/COleDataSource::CacheData.md)|Angebotdaten in einem angegebenen Format mit einer **STGMEDIUM**\-Struktur.|  
|[COleDataSource::CacheGlobalData](../Topic/COleDataSource::CacheGlobalData.md)|Stellt Daten in einem angegebenen Format mit `HGLOBAL` an.|  
|[COleDataSource::DelayRenderData](../Topic/COleDataSource::DelayRenderData.md)|Stellt Daten in einem angegebenen Format mithilfe des verzögerten Rendering an.|  
|[COleDataSource::DelayRenderFileData](../Topic/COleDataSource::DelayRenderFileData.md)|Stellt Daten in einem angegebenen Format in einem `CFile` Zeiger an.|  
|[COleDataSource::DelaySetData](../Topic/COleDataSource::DelaySetData.md)|Aufgerufen für jedes Format, das in `OnSetData` unterstützt wird.|  
|[COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)|Führt Drag & Drop\-Operationen mit einer Datenquelle aus.|  
|[COleDataSource::Empty](../Topic/COleDataSource::Empty.md)|Leert das `COleDataSource`\-Objekt von Daten.|  
|[COleDataSource::FlushClipboard](../Topic/COleDataSource::FlushClipboard.md)|Gibt alle Daten in die Zwischenablage.|  
|[COleDataSource::GetClipboardOwner](../Topic/COleDataSource::GetClipboardOwner.md)|Überprüft, ob die Daten, die in der Zwischenablage abgelegt werden, immer noch vorhanden sind.|  
|[COleDataSource::OnRenderData](../Topic/COleDataSource::OnRenderData.md)|Ruft Daten als Teil des verzögerten Renderings ab.|  
|[COleDataSource::OnRenderFileData](../Topic/COleDataSource::OnRenderFileData.md)|Ruft Daten in `CFile` als Teil des verzögerten Renderings ab.|  
|[COleDataSource::OnRenderGlobalData](../Topic/COleDataSource::OnRenderGlobalData.md)|Ruft Daten in `HGLOBAL` als Teil des verzögerten Renderings ab.|  
|[COleDataSource::OnSetData](../Topic/COleDataSource::OnSetData.md)|Aufgerufen, um die Daten in `COleDataSource` zu ersetzen Objekts.|  
|[COleDataSource::SetClipboard](../Topic/COleDataSource::SetClipboard.md)|Setzt ein `COleDataSource`\-Objekt in der Zwischenablage.|  
  
## Hinweise  
 Sie können OLE\-Datenquellen direkt erstellen.  Sie erstellen die [COleClientItem](../../mfc/reference/coleclientitem-class.md) und [COleServerItem](../../mfc/reference/coleserveritem-class.md)\-Klassen OLE\-Datenquellen als Reaktion auf ihre `CopyToClipboard` und `DoDragDrop`\-Memberfunktionen.  Siehe [COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md) für eine kurze Beschreibung.  Überschreiben Sie die `OnGetClipboardData`\-Memberfunktion der Clientelement\- oder Serverelementklasse, um zusätzliche Zwischenablageformate den Daten in der OLE\-Datenquelle hinzuzufügen, die für die `CopyToClipboard` oder `DoDragDrop`\-Memberfunktion erstellt wird.  
  
 Wenn Sie Daten für eine Übertragung vorbereiten möchten, sollten Sie ein Objekt dieser Klasse erstellen und mit den Daten mithilfe der meisten entsprechende Methode für die Daten gefüllt.  Die Methode, die sie in eine Datenquelle eingefügt wird, wird direkt davon beeinflusst, ob die Daten sofort \(direktes Rendering\) oder bei Bedarf angegeben werden \(verzögertes Rendering\).  Für jedes Zwischenablageformat, in dem Sie Daten aus dem Übergeben des verwendet werden bereitstellen Zwischenablageformats \(und der optionalen [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)\-Struktur\), Aufruf [DelayRenderData](../Topic/COleDataSource::DelayRenderData.md).  
  
 Weitere Informationen über Datenquellen und Datenübertragung, finden Sie im Artikel [Datenobjekte und Datenquellen \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md).  Außerdem wird der Artikel [Zwischenablage\-Themen](../../mfc/clipboard.md) den OLE\-Zwischenablagemechanismus.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC\-Beispiel HIERSVR](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel OCLIENT](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDataObject Class](../../mfc/reference/coledataobject-class.md)