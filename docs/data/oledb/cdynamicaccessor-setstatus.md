---
title: "CDynamicAccessor::SetStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetStatus"
  - "ATL::CDynamicAccessor::SetStatus"
  - "CDynamicAccessor.SetStatus"
  - "ATL.CDynamicAccessor.SetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetStatus-Methode"
ms.assetid: 6db82694-e87d-4bf8-a7e3-5765cf6abff9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt den Status der angegebenen Spalte fest.  
  
## Syntax  
  
```  
  
      bool SetStatus(   
   DBORDINAL nColumn,   
   DBSTATUS status    
) throw( );  
bool SetStatus(   
   const CHAR* pColumnName,   
   DBSTATUS status    
) throw( );  
bool SetStatus(   
   const WCHAR* pColumnName,   
   DBSTATUS status    
) throw( );  
```  
  
#### Parameter  
 `nColumn`  
 \[in\] Spaltennummer.  Spaltennummern beginnen mit 1.  Ein Wert von 0 werden die Lesezeichenspalte an, falls welche vorhanden.  
  
 *status*  
 \[in\] Der Spaltenstatus.  Siehe [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in *der OLE DB\-Programmierreferenz* weitere Informationen.  
  
 `pColumnName`  
 \[in\] Ein Zeiger auf eine Zeichenfolge, die den Spaltennamen enthält.  
  
## Rückgabewert  
 Gibt **true** zurück, wenn der angegebene Spaltenstatus erfolgreich festgelegt wird.  Andernfalls gibt diese Funktion **false** zurück.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)