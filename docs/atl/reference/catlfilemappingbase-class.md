---
title: "CAtlFileMappingBase Class"
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
  - "ATL.CAtlFileMappingBase"
  - "ATL::CAtlFileMappingBase"
  - "CAtlFileMappingBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFileMappingBase class"
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 20
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlFileMappingBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Speicherabbilddatei dar.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CAtlFileMappingBase  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](../Topic/CAtlFileMappingBase::CAtlFileMappingBase.md)|Der \-Konstruktor.|  
|[CAtlFileMappingBase::~CAtlFileMappingBase](../Topic/CAtlFileMappingBase::~CAtlFileMappingBase.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](../Topic/CAtlFileMappingBase::CopyFrom.md)|Rufen Sie diese Methode auf, um aus einem Dateizuordnungsobjekt zu kopieren.|  
|[CAtlFileMappingBase::GetData](../Topic/CAtlFileMappingBase::GetData.md)|Rufen Sie diese Methode auf, um die Daten von einem Dateizuordnungsobjekt abzurufen.|  
|[CAtlFileMappingBase::GetHandle](../Topic/CAtlFileMappingBase::GetHandle.md)|Rufen Sie diese Methode auf, um das Dateihandle zurückzugeben.|  
|[CAtlFileMappingBase::GetMappingSize](../Topic/CAtlFileMappingBase::GetMappingSize.md)|Rufen Sie diese Methode auf, um die Zuordnungsgröße eines Dateizuordnungsobjekt abzurufen.|  
|[CAtlFileMappingBase::MapFile](../Topic/CAtlFileMappingBase::MapFile.md)|Rufen Sie diese Methode auf, um ein Dateizuordnungsobjekt zu erstellen.|  
|[CAtlFileMappingBase::MapSharedMem](../Topic/CAtlFileMappingBase::MapSharedMem.md)|Rufen Sie diese Methode auf, um ein Dateizuordnungsobjekt zu erstellen, das allen Prozessen zulässt.|  
|[CAtlFileMappingBase::OpenMapping](../Topic/CAtlFileMappingBase::OpenMapping.md)|Rufen Sie diese Methode auf, um ein Handle für Dateizuordnungsobjekt zurückzugeben.|  
|[CAtlFileMappingBase::Unmap](../Topic/CAtlFileMappingBase::Unmap.md)|Rufen Sie diese Methode auf, um ein Dateizuordnungsobjekt aufzuheben.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator \=](../Topic/CAtlFileMappingBase::operator%20=.md)|Legt das aktuelle Dateizuordnungsobjekt zu einem anderen Dateizuordnungsobjekt fest.|  
  
## Hinweise  
 Dateizuordnung ist die Zuordnung des Inhalts einer Datei mit einem Teil des virtuellen Adressbereichs eines Prozesses.  Diese Klasse stellt Methoden zum Erstellen von Dateizuordnungsobjekten bereit, die Programme ermöglichen, auf Daten zuzugreifen und problemlos freizugeben.  
  
 Weitere Informationen finden Sie unter [Dateizuordnung](http://msdn.microsoft.com/library/windows/desktop/aa366556) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atlfile.h  
  
## Siehe auch  
 [CAtlFileMapping Class](../../atl/reference/catlfilemapping-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)