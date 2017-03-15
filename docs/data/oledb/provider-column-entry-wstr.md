---
title: "PROVIDER_COLUMN_ENTRY_WSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_WSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_WSTR-Makro"
ms.assetid: 70630bd5-d782-473b-9777-aebbbf5321c5
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROVIDER_COLUMN_ENTRY_WSTR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine bestimmte Spalte dar, die vom Anbieter unterstützt wird.  
  
## Syntax  
  
```  
  
PROVIDER_COLUMN_ENTRY_WSTR(  
name  
, ordinal, member )  
```  
  
#### Parameter  
 *Name*  
 \[in\] der Spaltenname.  
  
 `ordinal`  
 \[in\] Spaltennummer.  Sofern, dass die Spalte eine Lesezeichenspalte ist, darf die Spaltennummer nicht 0 sein.  
  
 `member`  
 \[in\] Die Membervariable in der Datenklasse, die die Daten speichert.  
  
## Hinweise  
 Verwenden Sie dieses Makro, wenn die Spaltendaten eine NULL\-Zeichenfolge beendete Unicode\-Zeichenfolge sind, [DBTYPE\_WSTR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)