---
title: "CAccessorBase-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CAccessorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorBase-Klasse"
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorBase-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alle Accessoren in den OLE DB\-Vorlagen werden von dieser Klasse abgeleitet.  `CAccessorBase` ermöglicht es einem Rowset, um mehrere Accessoren zu verwalten.  Es bietet auch Bindung für Parameter und Ausgabespaltenbindungen bereit.  
  
## Syntax  
  
```  
// Replace with syntax  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[Schließen](../../data/oledb/caccessorbase-close.md)|Schließt die Accessoren.|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|Ruft das Accessorhandle ab.|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|Ruft die Anzahl der Accessoren ab, die von der Klasse erstellt werden.|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|Testet, ob der angegebene ein Accessor ob ist.|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|Befreit die Accessoren.|  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)