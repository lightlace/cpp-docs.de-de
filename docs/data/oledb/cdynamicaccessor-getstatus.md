---
title: "CDynamicAccessor::GetStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::GetStatus"
  - "CDynamicAccessor.GetStatus"
  - "ATL.CDynamicAccessor.GetStatus"
  - "CDynamicAccessor::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus-Methode"
ms.assetid: 8f1aba69-5c2c-4ca7-ad84-7b4b27995eb8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Status der angegebenen Spalte ab.  
  
## Syntax  
  
```  
  
      bool GetStatus(   
   DBORDINAL nColumn,   
   DBSTATUS* pStatus    
) const throw( );  
bool GetStatus(  
   const CHAR* pColumnName,  
   DBSTATUS* pStatus   
) const throw( );  
bool GetStatus(  
   const WCHAR* pColumnName,  
   DBSTATUS* pStatus   
) const throw( );  
```  
  
#### Parameter  
 `nColumn`  
 \[in\] Spaltennummer.  Spaltennummern beginnen mit 1.  Ein Wert von 0 werden die Lesezeichenspalte an, falls welche vorhanden.  
  
 `pColumnName`  
 \[in\] Ein Zeiger auf eine Zeichenfolge, die den Spaltennamen enthält.  
  
 `pStatus`  
 \[out\] Ein Zeiger auf die Variablen, die den Spaltenstatus enthält.  Siehe [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in *der OLE DB\-Programmierreferenz* weitere Informationen.  
  
## Rückgabewert  
 Gibt **true** zurück, wenn die angegebenen Spalte gefunden wird.  Andernfalls gibt diese Funktion **false** zurück.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)