---
title: "IRowsetUpdateImpl::GetPendingRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetUpdateImpl::GetPendingRows"
  - "GetPendingRows"
  - "IRowsetUpdateImpl.GetPendingRows"
  - "ATL::IRowsetUpdateImpl::GetPendingRows"
  - "ATL.IRowsetUpdateImpl.GetPendingRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetPendingRows-Methode"
ms.assetid: 2d1ef748-da6d-4184-98dc-096427358dfd
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetUpdateImpl::GetPendingRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt eine Liste der Zeilen mit ausstehenden Änderungen zurück.  
  
## Syntax  
  
```  
  
      STDMETHOD ( GetPendingRows )(  
   HCHAPTER /* hReserved */,  
   DBPENDINGSTATUS dwRowStatus,  
   DBCOUNTITEM* pcPendingRows,  
   HROW** prgPendingRows,  
   DBPENDINGSTATUS** prgPendingStatus   
);  
```  
  
#### Parameter  
 `hReserved`  
 \[in\] entspricht dem Parameter `hChapter` in [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx).  
  
 Für weitere Parameter finden Sie unter [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetUpdateImpl\-Klasse](../../data/oledb/irowsetupdateimpl-class.md)