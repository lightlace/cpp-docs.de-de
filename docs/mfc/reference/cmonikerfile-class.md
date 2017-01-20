---
title: "CMonikerFile Class"
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
  - "CMonikerFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonikerFile class"
  - "IMoniker interface"
  - "IMoniker interface, Bindung"
  - "monikers, MFC"
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CMonikerFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Stream von Daten \([IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)\) mit dem Namen durch [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) dar.  
  
## Syntax  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](../Topic/CMonikerFile::CMonikerFile.md)|Erstellt ein `CMonikerFile`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMonikerFile::Close](../Topic/CMonikerFile::Close.md)|Trennt und gibt den Stream frei und gibt den Moniker frei.|  
|[CMonikerFile::Detach](../Topic/CMonikerFile::Detach.md)|Trennt `IMoniker` von diesem `CMonikerFile`\-Objekt.|  
|[CMonikerFile::GetMoniker](../Topic/CMonikerFile::GetMoniker.md)|Gibt den aktuellen Moniker zurück.|  
|[CMonikerFile::Open](../Topic/CMonikerFile::Open.md)|Öffnet die angegebene Datei, um ein Stream.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](../Topic/CMonikerFile::CreateBindContext.md)|Erhält der Bindungskontext oder erstellt einen standardmäßigen initialisierten Bindungskontext.|  
  
## Hinweise  
 Ein Moniker enthält Informationen ähnlich wie ein Pfadnamen zu einer Datei.  Wenn Sie einen Zeiger auf `IMoniker`\-Schnittstelle eines Monikerobjekts haben, können Sie abrufen Zugriff auf die identifizierten Datei ohne verfügen alle anderen bestimmten Informationen darüber, wo die Datei tatsächlich befindet.  
  
 Ist von `COleStreamFile`, nimmt `CMonikerFile` einen Moniker oder eine Zeichenfolgendarstellung, die in einen Moniker und Bindungen in den Stream ausführen kann, für den der Moniker ein Name ist.  Sie können zu diesem Stream dann lesen und schreiben.  Das echte Ziel von `CMonikerFile` ist, einfachen Zugriff auf `IStream` s zu ermöglichen, das von `IMoniker` s genannt wird, damit Sie nicht in einem Stream binden müssen sich, jedoch hat `CFile`\-Funktionen in den Stream.  
  
 `CMonikerFile` kann nicht verwendet werden, um zu nichts anderes als einen Stream zu binden.  Wenn Sie den Speicher oder einem Objekt binden möchten, müssen Sie die `IMoniker`\-Schnittstelle direkt verwenden.  
  
 Weitere Informationen über Streams und Moniker, finden Sie unter [COleStreamFile](../../mfc/reference/colestreamfile-class.md) in der *MFC\-Referenz* und in [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) und [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [COleStreamFile Class](../../mfc/reference/colestreamfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)