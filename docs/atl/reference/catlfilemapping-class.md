---
title: "CAtlFileMapping Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlFileMapping<T>"
  - "ATL.CAtlFileMapping"
  - "ATL::CAtlFileMapping"
  - "CAtlFileMapping"
  - "ATL.CAtlFileMapping<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFileMapping class"
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAtlFileMapping Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Speicherabbilddatei dar und fügt einen Typumwandlungsoperator an Methoden von [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md) hinzu.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
typename T= char  
>  
class CAtlFileMapping :  
public CAtlFileMappingBase  
```  
  
#### Parameter  
 `T`  
 Der Typ der Daten verwendet für den Umwandlungsoperator.  
  
## Mitglieder  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlFileMapping::operator T\*](../Topic/CAtlFileMapping::operator%20T*.md)|Ermöglicht die implizite Konvertierung von `CAtlFileMapping`\-Objekten zu `T`**\***.|  
  
## Hinweise  
 Diese Klasse fügt einen einzelnen Umwandlungsoperator hinzu, um die implizite Konvertierung von `CAtlFileMapping`\-Objekten zu `T`**\*** zuzulassen.  Andere Member werden von der Basisklasse, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md) angegeben.  
  
## Vererbungshierarchie  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## Anforderungen  
 **Header:** atlfile.h  
  
## Siehe auch  
 [CAtlFileMappingBase Class](../../atl/reference/catlfilemappingbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)