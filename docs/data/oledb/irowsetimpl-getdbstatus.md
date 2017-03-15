---
title: "IRowsetImpl::GetDBStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetDBStatus"
  - "IRowsetImpl.GetDBStatus"
  - "IRowsetImpl::GetDBStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDBStatus-Methode"
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::GetDBStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den `DBSTATUS` Statusflags für das angegebene Feld zurück.  
  
## Syntax  
  
```  
  
      virtual DBSTATUS GetDBStatus(  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames   
);  
```  
  
#### Parameter  
 \[in\] `currentRow`  
 Die aktuelle Zeile.  
  
 \[in\] `columnNames`  
 Die Spalte, für die Status angefordert wird.  
  
## Rückgabewert  
 Die [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx)\-Flags für die Spalte.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetImpl\-Klasse](../../data/oledb/irowsetimpl-class.md)