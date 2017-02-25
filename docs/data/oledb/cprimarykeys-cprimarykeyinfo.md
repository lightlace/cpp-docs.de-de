---
title: "CPrimaryKeys, CPrimaryKeyInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_nOrdinal"
  - "m_szTableSchema"
  - "m_nColumnPropID"
  - "CPrimaryKeys"
  - "COLUMN_GUID"
  - "CPrimaryKeyInfo"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "ORDINAL"
  - "m_szTableName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "CPrimaryKeyInfo-Parameterklasse"
  - "CPrimaryKeys typedef-Klasse"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_nOrdinal"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "ORDINAL-Datenmember"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: c27b97a4-a156-4f66-89e3-95f85d7d6281
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CPrimaryKeys, CPrimaryKeyInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rufen Sie die typedef\-Klasse **CPrimaryKeys** auf, um dessen Parameterklasse **CPrimaryKeyInfo** zu implementieren.  
  
## Hinweise  
 Siehe [Schemarowset\-Klassen und typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) weitere Informationen zur Verwendung von Informationen.  
  
 Diese Klasse identifiziert die Primärschlüsselspalten, die im Katalog von einem bestimmten Benutzer definiert werden.  
  
 Die folgende Tabelle zeigt die Klassendatenmember und ihre entsprechenden OLE DB Spalten auf.  Siehe [PRIMARY\_KEYS\-Rowset](https://msdn.microsoft.com/en-us/library/ms714362.aspx) in *der OLE DB\-Programmierreferenz* weitere Informationen über das Schema und Spalten.  
  
|Datenmember|OLE DB\-Spalten|  
|-----------------|---------------------|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
|m\_nOrdinal|ORDINALWERT|  
  
## Voraussetzungen  
 **Header:**  atldbsch.h  
  
## Siehe auch  
 [CRestrictions\-Klasse](../../data/oledb/crestrictions-class.md)