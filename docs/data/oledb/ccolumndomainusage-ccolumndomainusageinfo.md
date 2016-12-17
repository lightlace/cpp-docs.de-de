---
title: "CColumnDomainUsage, CColumnDomainUsageInfo"
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
  - "m_szTableSchema"
  - "m_szCatalog"
  - "m_nColumnPropID"
  - "CColumnDomainUsageInfo"
  - "COLUMN_GUID"
  - "DOMAIN_NAME"
  - "m_szColumnName"
  - "DOMAIN_SCHEMA"
  - "DOMAIN_CATALOG"
  - "m_szTableCatalog"
  - "m_szSchema"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "CColumnDomainUsage"
  - "m_szTableName"
  - "m_szName"
  - "COLUMN_DOMAIN_USAGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumnDomainUsage-Typedefklasse"
  - "CColumnDomainUsageInfo-Parameterklasse"
  - "COLUMN_DOMAIN_USAGE"
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "DOMAIN_CATALOG"
  - "DOMAIN_NAME"
  - "DOMAIN_SCHEMA"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_szCatalog"
  - "m_szColumnName"
  - "m_szName"
  - "m_szSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 5ff331f1-b99c-4002-9e04-367708c5759f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CColumnDomainUsage, CColumnDomainUsageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rufen Sie die typedef\-Klasse **CColumnDomainUsage** auf, um dessen Parameterklasse **CColumnDomainUsageInfo** zu implementieren.  
  
## Hinweise  
 Siehe [Schemarowset\-Klassen und typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) weitere Informationen zur Verwendung von Informationen.  
  
 Diese Klasse identifiziert die Spalten, definiert im Katalog, die von einer Domäne abhängig sind, die im Katalog definiert ist und einen bestimmten Benutzer gehört ist.  
  
 Die folgende Tabelle zeigt die Klassendatenmember und ihre entsprechenden OLE DB Spalten auf.  Siehe [COLUMN\_DOMAIN\_USAGE\-Rowset](https://msdn.microsoft.com/en-us/library/ms711240.aspx) in *der OLE DB\-Programmierreferenz* weitere Informationen über das Schema und Spalten.  
  
|Datenmember|OLE DB\-Spalten|  
|-----------------|---------------------|  
|m\_szCatalog|DOMAIN\_CATALOG|  
|m\_szSchema|DOMAIN\_SCHEMA|  
|m\_szName|DOMAIN\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
  
## Voraussetzungen  
 **Header:**  atldbsch.h  
  
## Siehe auch  
 [CRestrictions\-Klasse](../../data/oledb/crestrictions-class.md)