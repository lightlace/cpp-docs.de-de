---
title: "COleStreamFile Class"
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
  - "COleStreamFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleStreamFile class"
  - "data streams [C++]"
  - "data streams [C++], OLE"
  - "OLE [C++], streams of data"
  - "OLE structured storage [C++]"
  - "streams [C++], OLE"
  - "structured storage in OLE"
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# COleStreamFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Stream von Daten \(`IStream`\) in einer Verbunddatei als Teil des OLE strukturierten Speicher dar.  
  
## Syntax  
  
```  
class COleStreamFile : public CFile  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](../Topic/COleStreamFile::COleStreamFile.md)|Erstellt ein `COleStreamFile`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleStreamFile::Attach](../Topic/COleStreamFile::Attach.md)|Ordnet einen Stream mit dem Objekt zu.|  
|[COleStreamFile::CreateMemoryStream](../Topic/COleStreamFile::CreateMemoryStream.md)|Stellt einen Stream aus globalen Arbeitsspeicher erstellt und ordnet ihn dem Objekt zu.|  
|[COleStreamFile::CreateStream](../Topic/COleStreamFile::CreateStream.md)|Stellt einen Stream erstellt und ordnet ihn dem Objekt zu.|  
|[COleStreamFile::Detach](../Topic/COleStreamFile::Detach.md)|Hebt den Stream aus Objekt Zuordnung auf.|  
|[COleStreamFile::GetStream](../Topic/COleStreamFile::GetStream.md)|Gibt den aktuellen Stream zurück.|  
|[COleStreamFile::OpenStream](../Topic/COleStreamFile::OpenStream.md)|Öffnet einen Stream sicher und ordnet ihn dem Objekt zu.|  
  
## Hinweise  
 Ein Objekt `IStorage` muss vorhanden sein, bevor der Stream geöffnet oder erstellt werden kann, es sei denn, es ist ein Arbeitsspeicherstream ist.  
  
 `COleStreamFile`\-Objekte werden genau wie [Die C\-Datei](../../mfc/reference/cfile-class.md)\-Objekte bearbeitet.  
  
 Weitere Informationen zum Bearbeiten von Streams und von Speichern, finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md).  
  
 Weitere Informationen finden Sie unter [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) und [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)