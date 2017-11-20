---
title: "IRowsetImpl::RefRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetImpl::RefRows"
  - "ATL.IRowsetImpl.RefRows"
  - "IRowsetImpl.RefRows"
  - "RefRows"
  - "IRowsetImpl::RefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RefRows-Methode"
ms.assetid: 1c048a2a-65dc-4bba-9c81-a23c0dc249c8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::RefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird von [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) auf den Inkrement oder geben einen Verweiszähler einem vorhandenen Zeilenhandle frei.  
  
## Syntax  
  
```  
  
      HRESULT RefRows(  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd   
);  
```  
  
#### Parameter  
 Siehe [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Rückgabewert  
 Ein Standard\- `HRESULT`\-Wert.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetImpl\-Klasse](../../data/oledb/irowsetimpl-class.md)   
 [CSimpleRow\-Klasse](../../data/oledb/csimplerow-class.md)