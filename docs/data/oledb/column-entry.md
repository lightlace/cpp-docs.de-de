---
title: "COLUMN_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY-Makro"
ms.assetid: a10aef29-6d70-49ec-b572-5b5c4abe1b46
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# COLUMN_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Bindung im Rowset zur jeweiligen Spalte im Rowset dar.  
  
## Syntax  
  
```  
  
COLUMN_ENTRY(  
nOrdinal  
,   
data  
 )  
  
```  
  
#### Parameter  
 Siehe [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE* DB\-Programmierreferenz.  
  
 `nOrdinal`  
 \[in\] Spaltennummer.  
  
 `data`  
 \[in\] der entsprechenden Datenmember im Benutzerdatensatz.  
  
## Hinweise  
 Das Makro `COLUMN_ENTRY` wird an den folgenden Orten:  
  
-   Zwischen den Makros [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) und [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md).  
  
-   Zwischen den Makros [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) und [END\_ACCESSOR](../../data/oledb/end-accessor.md).  
  
-   Zwischen den Makros [BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md) und [END\_PARAM\_MAP](../../data/oledb/end-param-map.md).  
  
## Beispiel  
 Siehe die Beispiele in den Makrothemen, [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) und [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [COLUMN\_ENTRY\_TYPE](../../data/oledb/column-entry-type.md)   
 [COLUMN\_ENTRY\_TYPE\_SIZE](../../data/oledb/column-entry-type-size.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)