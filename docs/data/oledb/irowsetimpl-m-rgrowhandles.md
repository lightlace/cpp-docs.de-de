---
title: "IRowsetImpl::m_rgRowHandles"
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
  - "IRowsetImpl::m_rgRowHandles"
  - "IRowsetImpl.m_rgRowHandles"
  - "m_rgRowHandles"
  - "ATL::IRowsetImpl::m_rgRowHandles"
  - "ATL.IRowsetImpl.m_rgRowHandles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_rgRowHandles"
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::m_rgRowHandles
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Zuordnung von Zeilenhandles gerade enthalten vom Anbieter in Reaktion auf `GetNextRows`.  
  
## Syntax  
  
```  
  
MapClass  
 m_rgRowHandles;  
  
```  
  
## Hinweise  
 Zeilenhandles entfernt werden, indem `ReleaseRows` aufgerufen wird.  Siehe [IRowsetImpl\-Übersicht](../../data/oledb/irowsetimpl-class.md) für die Definition von *MapClass*.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetImpl\-Klasse](../../data/oledb/irowsetimpl-class.md)