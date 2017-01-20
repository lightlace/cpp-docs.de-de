---
title: "IRowsetUpdateImpl::m_mapCachedData"
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
  - "IRowsetUpdateImpl.m_mapCachedData"
  - "IRowsetUpdateImpl::m_mapCachedData"
  - "m_mapCachedData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_mapCachedData"
ms.assetid: 65131743-8580-48c8-bb22-68f17c9dfa13
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::m_mapCachedData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Zuordnung, die die ursprünglichen Daten für den verzögerten Operation enthält.  
  
## Syntax  
  
```  
  
      CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### Parameter  
 `hRow`  
 Handle auf Linien für die Daten.  
  
 `pData`  
 Ein Zeiger auf die Daten zwischengespeichert werden.  Die Daten sind von Typ *Speicher* \(die Benutzerdatensatz\-Klasse\).  Siehe das *Speichervorlagenargument* in [IRowsetUpdateImpl\-Klasse](../../data/oledb/irowsetupdateimpl-class.md).  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetUpdateImpl\-Klasse](../../data/oledb/irowsetupdateimpl-class.md)