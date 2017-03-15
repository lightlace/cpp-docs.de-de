---
title: "IRowsetIdentityImpl::IsSameRow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IsSameRow"
  - "IRowsetIdentityImpl.IsSameRow"
  - "ATL.IRowsetIdentityImpl.IsSameRow"
  - "IRowsetIdentityImpl::IsSameRow"
  - "ATL::IRowsetIdentityImpl::IsSameRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsSameRow-Methode"
ms.assetid: e35ad54e-73f1-4dc0-8d8c-9e98202baf0a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetIdentityImpl::IsSameRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht zwei Zeilenhandles, um zu sehen, wenn sie dieselbe Zeile zugreifen.  
  
## Syntax  
  
```  
  
      STDMETHOD( IsSameRow )(  
   HROW hThisRow,  
   HROW hThatRow   
);  
```  
  
#### Parameter  
 Siehe [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Um Zeilenhandles vergleichen, wandelt diese Methode **HROW** die Handles zu **RowClass** um Member und `memcmp` aufgerufen Zeigern auf.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetIdentityImpl\-Klasse](../../data/oledb/irowsetidentityimpl-class.md)