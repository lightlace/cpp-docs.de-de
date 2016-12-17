---
title: "BLOB_ENTRY"
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
  - "BLOB_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_ENTRY-Makro"
ms.assetid: 89e40678-0869-49ed-b502-0fa2630a9081
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# BLOB_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird mit `BEGIN_COLUMN_MAP` und `END_COLUMN_MAP`, um ein Binary Large Object \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\) zu binden.  
  
## Syntax  
  
```  
  
BLOB_ENTRY(  
nOrdinal  
,  
 IID  
,   
flags  
,   
data  
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
  
## Beispiel  
 Siehe [Wie kann ich ein BLOB abgerufen werden?](../../data/oledb/retrieving-a-blob.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB\_ENTRY\_LENGTH\_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB\_ENTRY\_STATUS](../../data/oledb/blob-entry-status.md)