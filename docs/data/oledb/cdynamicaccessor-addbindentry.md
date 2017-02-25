---
title: "CDynamicAccessor::AddBindEntry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::AddBindEntry"
  - "AddBindEntry"
  - "CDynamicAccessor.AddBindEntry"
  - "CDynamicAccessor::AddBindEntry"
  - "ATL.CDynamicAccessor.AddBindEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddBindEntry-Methode"
ms.assetid: 8f139376-7db3-4193-ba3b-63fe938ffa79
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::AddBindEntry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt einem Bindungseintrag den Ausgabespalten hinzu.  
  
## Syntax  
  
```  
  
      HRESULT AddBindEntry(   
   const DBCOLUMNINFO& info    
) throw( );  
```  
  
#### Parameter  
 `info`  
 \[in\] Eine **DBCOLUMNINFO**\-Struktur, die Spalteninformationen enthält.  Siehe, dass "DBCOLUMNINFO" in [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in der *OLE* DB\-Programmierreferenz strukturiert.  
  
## Rückgabewert  
 Einer der Standard\- `HRESULT`\-Werte.  
  
## Hinweise  
 Verwenden Sie diese Methode, wenn Sie den Standardaccessor überschreiben, der mit `CDynamicAccessor` erstellt wird \(siehe [Wie rufe ich Daten ab?](../../data/oledb/fetching-data.md)\).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)