---
title: "COLUMN_ENTRY_LENGTH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_LENGTH-Makro"
ms.assetid: 1758babf-204c-4d1d-b82a-f9a607072e9a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_ENTRY_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Bindung im Rowset zur jeweiligen Spalte in der Datenbank dar.  
  
## Syntax  
  
```  
  
COLUMN_ENTRY_LENGTH(  
nOrdinal  
,   
data  
,   
length  
 )  
  
```  
  
#### Parameter  
 Siehe [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE* DB\-Programmierreferenz.  
  
 `nOrdinal`  
 \[in\] Spaltennummer, beginnend mit einer.  Lesezeichen entspricht Spalte null.  
  
 `data`  
 \[in\] der entsprechenden Datenmember im Benutzerdatensatz.  
  
 *length*  
 \[in\] die Spaltenlänge gebunden werden Variablen.  
  
## Hinweise  
 Dieses Makro unterstützt die *Längen* variable.  Es wird in den folgenden Stellen verwendet:  
  
-   Zwischen den Makros [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) und [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md).  
  
-   Zwischen den Makros [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) und [END\_ACCESSOR](../../data/oledb/end-accessor.md).  
  
-   Zwischen den Makros [BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md) und [END\_PARAM\_MAP](../../data/oledb/end-param-map.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)