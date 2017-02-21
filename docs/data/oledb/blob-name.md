---
title: "BLOB_NAME | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_NAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME-Makro"
ms.assetid: 757acd0d-946d-447d-937e-94ecd700ba38
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_NAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird mit `BEGIN_COLUMN_MAP` und `END_COLUMN_MAP`, um ein Binary Large Object \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\) zu binden.  Wie auch [BLOB\_ENTRY](../../data/oledb/blob-entry.md), außer dass zu diesem Makro verwendet einen Spaltennamen anstelle einer Spaltennummer.  
  
## Syntax  
  
```  
  
BLOB_NAME(  
pszName  
,   
IID  
,   
flags  
,   
data )  
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
  
## Beispiel  
 Siehe [Wie kann ich ein BLOB abgerufen werden?](../../data/oledb/retrieving-a-blob.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME\_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB\_NAME\_STATUS](../../data/oledb/blob-name-status.md)