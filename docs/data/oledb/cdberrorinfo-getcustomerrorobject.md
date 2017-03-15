---
title: "CDBErrorInfo::GetCustomErrorObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo::GetCustomErrorObject"
  - "ATL.CDBErrorInfo.GetCustomErrorObject"
  - "CDBErrorInfo.GetCustomErrorObject"
  - "ATL::CDBErrorInfo::GetCustomErrorObject"
  - "GetCustomErrorObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCustomErrorObject-Methode"
ms.assetid: 295c053c-b76c-47a5-adfb-333e65d2df0d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDBErrorInfo::GetCustomErrorObject
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aufrufe [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx), einen Zeiger auf eine Schnittstelle auf einem benutzerdefinierten Fehlerobjekts zurückzugeben.  
  
## Syntax  
  
```  
  
      HRESULT GetCustomErrorObject(   
   ULONG ulRecordNum,   
   REFIID riid,   
   IUnknown** ppObject    
) const throw( );  
```  
  
#### Parameter  
 Siehe [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDBErrorInfo\-Klasse](../../data/oledb/cdberrorinfo-class.md)