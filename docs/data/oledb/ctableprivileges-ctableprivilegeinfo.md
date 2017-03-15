---
title: "CTablePrivileges, CTablePrivilegeInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szCatalog"
  - "m_bIsGrantable"
  - "IS_GRANTABLE"
  - "m_szType"
  - "m_szSchema"
  - "m_szGrantor"
  - "GRANTOR"
  - "GRANTEE"
  - "CTablePrivileges"
  - "CTablePrivilegeInfo"
  - "m_szName"
  - "m_szGrantee"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTablePrivilegeInfo-Parameterklasse"
  - "CTablePrivileges-Typedefklasse"
  - "GRANTEE"
  - "GRANTOR"
  - "IS_GRANTABLE"
  - "m_bIsGrantable"
  - "m_szCatalog"
  - "m_szGrantee"
  - "m_szGrantor"
  - "m_szName"
  - "m_szSchema"
  - "m_szType"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: ffcd6f73-022e-452a-8342-f2b9362d256b
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CTablePrivileges, CTablePrivilegeInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rufen Sie die typedef\-Klasse **CTablePrivileges** auf, um dessen Parameterklasse **CTablePrivilegeInfo** zu implementieren.  
  
## Hinweise  
 Siehe [Schemarowset\-Klassen und typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) weitere Informationen zur Verwendung von Informationen.  
  
 Diese Klasse identifiziert die Tabellen, die im Katalog definiert werden, die für einen spezifischen Benutzer zugänglich sind.  
  
 Die folgende Tabelle zeigt die Klassendatenmember und ihre entsprechenden OLE DB Spalten auf.  Siehe [TABLE\_PRIVILEGES\-Rowset](https://msdn.microsoft.com/en-us/library/ms725428.aspx) in *der OLE DB\-Programmierreferenz* weitere Informationen über das Schema und Spalten.  
  
|Datenmember|OLE DB\-Spalten|  
|-----------------|---------------------|  
|m\_szGrantor|GRANTOR|  
|m\_szGrantee|GRANTEE|  
|m\_szCatalog|TABLE\_CATALOG|  
|m\_szSchema|TABLE\_SCHEMA|  
|m\_szName|TABLE\_NAME|  
|m\_szType|PRIVILEGE\_TYPE|  
|m\_bIsGrantable|IS\_GRANTABLE|  
  
## Voraussetzungen  
 **Header:**  atldbsch.h  
  
## Siehe auch  
 [CRestrictions\-Klasse](../../data/oledb/crestrictions-class.md)