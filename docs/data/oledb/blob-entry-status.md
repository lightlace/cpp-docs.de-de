---
title: "BLOB_ENTRY_STATUS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_ENTRY_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_ENTRY_STATUS-Makro"
ms.assetid: 191007f4-dfcc-4ae2-a7fc-6f7899accc9f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_ENTRY_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird mit `BEGIN_COLUMN_MAP` oder `BEGIN_ACCESSOR_MAP`, ein Binary Large Object \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\) zu binden.  Wie auch [BLOB\_ENTRY](../../data/oledb/blob-entry.md), außer dass zu diesem Makro ruft auch der Status der BLOBspalte ab.  
  
## Syntax  
  
```  
  
BLOB_ENTRY_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
,   
status  
 )  
  
```  
  
#### Parameter  
 `nOrdinal`  
 \[in\] Spaltennummer.  
  
 *IIDs*  
 \[in\] GUID schließen Sie, wie **IDD\_ISequentialStream** an, verwendet, um das BLOB abzurufen.  
  
 `flags`  
 \[in\] Flags Speicher\-Modus, wie vom OLE strukturierte Speichermodell, \(beispielsweise **STGM\_READ**\) definiert.  
  
 `data`  
 \[in\] der entsprechenden Datenmember im Benutzerdatensatz.  
  
 *status*  
 \[out\] der Status des BLOBfelds.  
  
## Beispiel  
 Siehe [Wie kann ich ein BLOB abgerufen werden?](../../data/oledb/retrieving-a-blob.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB\_ENTRY\_LENGTH\_STATUS](../../data/oledb/blob-entry-length-status.md)