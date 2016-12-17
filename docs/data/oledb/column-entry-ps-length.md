---
title: "COLUMN_ENTRY_PS_LENGTH"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_PS_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_PS_LENGTH-Makro"
ms.assetid: d63ab895-a4df-4183-ac09-cf2311222408
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_ENTRY_PS_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Bindung im Rowset zur jeweiligen Spalte in der Datenbank dar.  
  
## Syntax  
  
```  
  
COLUMN_ENTRY_PS_LENGTH(  
nOrdinal  
,   
nPrecision  
,   
nScale  
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
  
 `nPrecision`  
 \[in\] Die maximale Genauigkeit der Spalte, die Sie binden möchten.  
  
 `nScale`  
 \[in\] die Skalierung der Spalte, die Sie binden möchten.  
  
 `data`  
 \[in\] der entsprechenden Datenmember im Benutzerdatensatz.  
  
 *length*  
 \[in\] die Spaltenlänge gebunden werden Variablen.  
  
## Hinweise  
 Ermöglicht Ihnen, die Genauigkeit und die Skala der Spalte anzugeben, die Sie binden möchten.  Dieses Makro unterstützt die *Längen* variable.  Es wird in den folgenden Stellen verwendet:  
  
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
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)