---
title: "IDBInitializeImpl::m_dwStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IDBInitializeImpl::m_dwStatus"
  - "IDBInitializeImpl.m_dwStatus"
  - "ATL.IDBInitializeImpl.m_dwStatus"
  - "IDBInitializeImpl::m_dwStatus"
  - "IDBInitializeImpl<T>::m_dwStatus"
  - "ATL.IDBInitializeImpl<T>.m_dwStatus"
  - "ATL::IDBInitializeImpl<T>::m_dwStatus"
  - "m_dwStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_dwStatus"
ms.assetid: 7621ccff-ca60-4b75-9c6a-c104bd0e2038
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# IDBInitializeImpl::m_dwStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Datenquellenflags.  
  
## Syntax  
  
```  
  
DWORD m_dwStatus;  
  
```  
  
## Hinweise  
 Diese Flags legen fest oder geben den Status von unterschiedlichen Attributen für das Datenquellenobjekt an.  Enthält eine oder mehrere der folgenden Werte: `enum`  
  
 `enum DATASOURCE_FLAGS {`  
  
 `DSF_MASK_INIT     = 0xFFFFF00F,`  
  
 `DSF_PERSIST_DIRTY = 0x00000001,`  
  
 `DSF_INITIALIZED   = 0x00000010,`  
  
 `};`  
  
|||  
|-|-|  
|**DSF\_MASK\_INIT**|Eine Maske, mit der Wiederherstellung von nicht initialisiertem Zustand zu aktivieren.|  
|**DSF\_PERSIST\_DIRTY**|Legen Sie fest, wenn Datenquellenobjekt Dauerhaftigkeit erfordert \(das heißt, wenn Änderungen entdeckt werden\).|  
|**DSF\_INITIALIZED**|Legen Sie fest, wenn Datenquelle initialisiert wurde.|  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IDBInitializeImpl\-Klasse](../../data/oledb/idbinitializeimpl-class.md)   
 [IDBInitializeImpl::IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)   
 [IDBInitializeImpl::Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)