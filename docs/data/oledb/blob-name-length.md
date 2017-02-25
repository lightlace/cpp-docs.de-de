---
title: "BLOB_NAME_LENGTH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_NAME_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME_LENGTH-Makro"
ms.assetid: 38150260-a127-486d-a7ab-0d01b731b6fd
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_NAME_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird mit `BEGIN_COLUMN_MAP` und `END_COLUMN_MAP`, um ein Binary Large Object \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\) zu binden.  Wie auch [BLOB\_NAME](../../data/oledb/blob-name.md), außer dass zu diesem Makro ruft auch Längen in Bytes in der BLOBdatenspalte ab.  
  
## Syntax  
  
```  
  
BLOB_NAME_LENGTH(  
pszName  
,   
IID  
,   
flags  
,   
data  
,   
length )  
```  
  
#### Parameter  
 `pszName`  
 \[in\] Ein Zeiger auf den Spaltennamen.  Der Name muss eine Unicode\-Zeichenfolge sein.  Sie können dies bewerkstelligen, indem Sie "L" vor dem Namen, zum Beispiel einfügen: `L"MyColumn"`.  
  
 *IIDs*  
 \[in\] GUID schließen Sie, wie **IDD\_ISequentialStream** an, verwendet, um das BLOB abzurufen.  
  
 `flags`  
 \[in\] Flags Speicher\-Modus, wie vom OLE strukturierte Speichermodell, \(beispielsweise **STGM\_READ**\) definiert.  
  
 `data`  
 \[in\] der entsprechenden Datenmember im Benutzerdatensatz.  
  
 *length*  
 \[out\] Die \(tatsächliche\) Länge in Bytes der BLOBspalte.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME](../../data/oledb/blob-name.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB\_NAME\_STATUS](../../data/oledb/blob-name-status.md)