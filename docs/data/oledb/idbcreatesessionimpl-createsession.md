---
title: "IDBCreateSessionImpl::CreateSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBCreateSessionImpl::CreateSession"
  - "IDBCreateSessionImpl.CreateSession"
  - "CreateSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSession-Methode"
ms.assetid: 035e5ddb-56e6-43b1-874d-89c0e40b103b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBCreateSessionImpl::CreateSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine neue Sitzung vom Datenquellenobjekt und die angeforderte Schnittstelle der neu erstellten Sitzung zurückkehren.  
  
## Syntax  
  
```  
  
      STDMETHOD(CreateSession)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession    
);  
```  
  
#### Parameter  
 Siehe [IDBCreateSession::CreateSession](https://msdn.microsoft.com/en-us/library/ms714942.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IDBCreateSessionImpl\-Klasse](../../data/oledb/idbcreatesessionimpl-class.md)