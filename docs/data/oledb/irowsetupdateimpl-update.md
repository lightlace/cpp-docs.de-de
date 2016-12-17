---
title: "IRowsetUpdateImpl::Update"
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
  - "ATL::IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl.Update"
  - "ATL.IRowsetUpdateImpl.Update"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Updatemethode"
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::Update
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sendet Änderungen, die an der Zeile seit dem letzten Sammeln oder die Aktualisierung vorgenommen werden.  
  
## Syntax  
  
```  
  
      STDMETHOD ( Update )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### Parameter  
 `hReserved`  
 \[in\] entspricht dem Parameter `hChapter` in [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx).  
  
 Für weitere Parameter finden Sie unter [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Änderungen werden gesendet, indem Sie [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md) aufrufen.  Der Consumer muss [CRowset::Update](../../data/oledb/crowset-update.md) aufrufen, damit die Änderungen wirksam werden.  Legen Sie *prgRowstatus* auf einen geeigneten Wert fest, wie unter [Zeilenstatus](https://msdn.microsoft.com/en-us/library/ms722752.aspx) in der *OLE* DB\-Programmierreferenz beschrieben.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetUpdateImpl\-Klasse](../../data/oledb/irowsetupdateimpl-class.md)