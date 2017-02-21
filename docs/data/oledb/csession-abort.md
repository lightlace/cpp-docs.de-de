---
title: "CSession::Abort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSession.Abort"
  - "CSession::Abort"
  - "ATL.CSession.Abort"
  - "ATL::CSession::Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Abort-Methode"
ms.assetid: 02413b20-c486-451f-b4d7-73a6e8065df8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CSession::Abort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Beendet die Transaktion.  
  
## Syntax  
  
```  
  
      HRESULT Abort(   
   BOID* pboidReason = NULL,   
   BOOL bRetaining = FALSE,   
   BOOL bAsync = FALSE    
) const throw( );  
```  
  
#### Parameter  
 Siehe [ITransaction::Abort](https://msdn.microsoft.com/en-us/library/ms709833.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CSession\-Klasse](../../data/oledb/csession-class.md)