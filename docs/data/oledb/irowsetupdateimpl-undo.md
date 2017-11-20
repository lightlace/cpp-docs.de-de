---
title: "IRowsetUpdateImpl::Undo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetUpdateImpl.Undo"
  - "ATL::IRowsetUpdateImpl::Undo"
  - "IRowsetUpdateImpl::Undo"
  - "IRowsetUpdateImpl.Undo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Undo-Methode"
ms.assetid: f3dc7764-050c-4322-9b2f-9ca772a0fb88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetUpdateImpl::Undo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt alle Änderungen an der Zeile seit dem letzten Sammeln oder das Update rückgängig.  
  
## Syntax  
  
```  
  
      STDMETHOD ( Undo )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### Parameter  
 `hReserved`  
 \[in\] entspricht dem Parameter `hChapter` in [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 *pcRowsUndone*  
 \[out\] entspricht dem Parameter `pcRows` in [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 *prgRowsUndone*  
 \[in\] entspricht dem *prgRows*\-Parameter in [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 Für weitere Parameter finden Sie unter [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetUpdateImpl\-Klasse](../../data/oledb/irowsetupdateimpl-class.md)