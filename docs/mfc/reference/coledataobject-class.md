---
title: "COleDataObject Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "IDataObject"
  - "COleDataObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zwischenablage [C++], MFC-Unterstützung"
  - "Zwischenablage [C++], OLE-Unterstützung"
  - "COleDataObject class"
  - "data transfer [C++]"
  - "data transfer [C++], OLE"
  - "drag and drop [C++], MFC-Unterstützung"
  - "IDataObject interface, MFC encapsulation"
  - "OLE [C++], uniform data transfer"
  - "OLE Clipboard [C++], Unterstützung"
  - "OLE data transfer [C++]"
  - "uniform data transfer"
  - "uniform data transfer, OLE"
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# COleDataObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird in den Datenübertragungen für das Abrufen von Daten in unterschiedlichen Formaten aus der Zwischenablage, per Drag & Drop oder einem eingebetteten OLE\-Element.  
  
## Syntax  
  
```  
class COleDataObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](../Topic/COleDataObject::COleDataObject.md)|Erstellt ein `COleDataObject`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDataObject::Attach](../Topic/COleDataObject::Attach.md)|Fügt das angegebene OLE\-Datenobjekt zu `COleDataObject` an.|  
|[COleDataObject::AttachClipboard](../Topic/COleDataObject::AttachClipboard.md)|Fügt das Datenobjekt an, das in der Zwischenablage ist.|  
|[COleDataObject::BeginEnumFormats](../Topic/COleDataObject::BeginEnumFormats.md)|Bereitet sich für eine oder mehrere folgenden `GetNextFormat` Aufrufe vor.|  
|[COleDataObject::Detach](../Topic/COleDataObject::Detach.md)|Trennt `IDataObject` das zugeordnete Objekt.|  
|[COleDataObject::GetData](../Topic/COleDataObject::GetData.md)|Kopiert Daten vom angefügten OLE\-Datenobjekt in einem angegebenen Format.|  
|[COleDataObject::GetFileData](../Topic/COleDataObject::GetFileData.md)|Kopiert Daten vom angefügten OLE\-Datenobjekt in einen `CFile` Zeiger im angegebenen Format.|  
|[COleDataObject::GetGlobalData](../Topic/COleDataObject::GetGlobalData.md)|Kopiert Daten vom angefügten OLE\-Datenobjekt in `HGLOBAL` im angegebenen Format.|  
|[COleDataObject::GetNextFormat](../Topic/COleDataObject::GetNextFormat.md)|Gibt das nächste verfügbare Datenformat zurück.|  
|[COleDataObject::IsDataAvailable](../Topic/COleDataObject::IsDataAvailable.md)|Überprüft, ob Daten in einem bestimmten Format verfügbar sind.|  
|[COleDataObject::Release](../Topic/COleDataObject::Release.md)|Trennt und gibt das zugeordnete `IDataObject`\-Objekt frei.|  
  
## Hinweise  
 `COleDataObject` hat keine Basisklasse.  
  
 Diese Arten von Datenübertragungen enthalten eine Quelle und ein Ziel.  Die Datenquelle wird wie ein Objekt der [COleDataSource](../../mfc/reference/coledatasource-class.md)\-Klasse implementiert.  Sobald eine Ziel\-Anwendung die Daten verfügt, die in ihr abgelegt werden, oder einen Einfügevorgang aus der Zwischenablage auszuführen aufgefordert wird, muss ein Objekt der `COleDataObject`\-Klasse erstellt werden.  
  
 Diese Klasse ermöglicht es Ihnen, zu bestimmen, ob die Daten in einem angegebenen Format vorhanden sind.  Sie können die verfügbaren Datenformaten oder die Überprüfung auch auflisten, ob ein bestimmtes Format und die Daten im Format bevorzugten dann abrufen verfügbar ist.  Objektabruf kann auf unterschiedliche Weise, einschließlich der Verwendung von [Die C\-Datei](../../mfc/reference/cfile-class.md), `HGLOBAL` oder einer **STGMEDIUM**\-Struktur ausgeführt werden.  
  
 Weitere Informationen finden Sie unter [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) die Struktur in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zur Verwendung von Datenobjekten in der Anwendung, finden Sie im Artikel [Datenobjekte und Datenquellen \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## Vererbungshierarchie  
 `COleDataObject`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC Sampling HIERSVR](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel OCLIENT](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDataSource Class](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [CView::OnDrop](../Topic/CView::OnDrop.md)