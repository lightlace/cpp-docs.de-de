---
title: "IRowsetLocateImpl::GetRowsAt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetRowsAt"
  - "IRowsetLocateImpl.GetRowsAt"
  - "ATL::IRowsetLocateImpl::GetRowsAt"
  - "IRowsetLocateImpl::GetRowsAt"
  - "ATL.IRowsetLocateImpl.GetRowsAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowsAt-Methode"
ms.assetid: 6aeb09dc-3aa8-4729-97a8-144dd27063f7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetLocateImpl::GetRowsAt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft das Zeilen Starten mit der Zeile, die durch einen UTC\-Offset von einem Lesezeichen angegeben wird.  
  
## Syntax  
  
```  
  
      STDMETHOD ( GetRowsAt )(  
   HWATCHREGION /* hReserved1 */,  
   HCHAPTER hReserved2,  
   DBBKMARK cbBookmark,  
   const BYTE* pBookmark,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows   
);  
```  
  
#### Parameter  
 Siehe [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Um von der Cursorposition stattdessen abzurufen, verwenden Sie [IRowset::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx).  
  
 `IRowsetLocateImpl::GetRowsAt` ändert nicht die Cursorposition.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetLocateImpl\-Klasse](../../data/oledb/irowsetlocateimpl-class.md)   
 [IRowsetLocateImpl::GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)