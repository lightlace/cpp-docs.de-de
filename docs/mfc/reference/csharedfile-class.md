---
title: "CSharedFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSharedFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSharedFile class"
  - "memory files"
  - "shared memory files"
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSharedFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CMemFile](../../mfc/reference/cmemfile-class.md) von abgeleitete Klasse, die freigegebene Arbeitsspeicherdateien unterstützt.  
  
## Syntax  
  
```  
class CSharedFile : public CMemFile  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](../Topic/CSharedFile::CSharedFile.md)|Erstellt ein `CSharedFile`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSharedFile::Detach](../Topic/CSharedFile::Detach.md)|Schließt die freigegebene Arbeitsspeicherdatei und gibt das Handle des Speicherblocks zurück.|  
|[CSharedFile::SetHandle](../Topic/CSharedFile::SetHandle.md)|Fügt die freigegebene Arbeitsspeicherdatei zu einem Speicherblock bei.|  
  
## Hinweise  
 Arbeitsspeicherdateien verhalten sich wie Datenträgerdateien, außer dass die Datei wird in RAM statt auf einem Datenträger gespeichert.  Eine Arbeitsspeicherdatei ist für schnelle temporäre Speicherung oder zum Übertragen von unformatierten Bytes oder serialisierter Objekten zwischen unabhängige Prozesse hilfreich.  
  
 Freigegebene Arbeitsspeicherdateien unterscheiden sich von anderen Arbeitsspeicherdateien in diesem Speicher für sie zugeordnet wird mit der [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows\-Funktion.  Die `CSharedFile`\-Klasse werden Daten in einem global reservierten Speicherblock \(erstellt mit **GlobalAlloc**\), und dieser Speicherblock kann mit DDE, der Zwischenablage oder anderer einheitlicher Datenübertragungsvorgänge OLE\/COM\-Plattform beispielsweise mithilfe `IDataObject` freigegeben werden.  
  
 **GlobalAlloc** gibt ein Handle `HGLOBAL` statt als Zeiger auf den Speicher, wie dem Zeiger zurück, der durch [malloc](../../c-runtime-library/reference/malloc.md) zurückgegeben wird.  Das `HGLOBAL` Handle wird in bestimmten Anwendungen benötigt.  Um beispielsweise Daten in die Zwischenablage ablegen benötigen Sie ein `HGLOBAL` Handle.  
  
 Beachten Sie, dass `CSharedFile` nicht Speicherabbilddateien verwendet, und die Daten können nicht zwischen Prozessen direkt freigegeben werden.  
  
 `CSharedFile`\-Objekte können ihren eigenen Speicher automatisch zuordnen, oder einen eigenen Speicherblock zum `CSharedFile`\-Objekt anfügen, indem Sie [CSharedFile::SetHandle](../Topic/CSharedFile::SetHandle.md) aufrufen.  In jedem Fall wird für das nicht der Arbeitsspeicherdatei automatisch in groß Inkrementen `nGrowBytes` zugeordnet, wenn `nGrowBytes` nicht Null ist.  
  
 Weitere Informationen finden Sie im Artikel [Dateien in MFC](../../mfc/files-in-mfc.md) und [Datei\-Behandlung](../../c-runtime-library/file-handling.md) in der Laufzeitbibliotheksreferenz.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## Anforderungen  
 **Header:**  afxadv.h  
  
## Siehe auch  
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)   
 [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)   
 [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590)