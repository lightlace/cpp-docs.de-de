---
title: CColumnPrivileges, CColumnPrivilegeInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- m_szTableSchema
- CColumnPrivileges
- m_bIsGrantable
- m_nColumnPropID
- m_szPrivilegeType
- COLUMN_GUID
- IS_GRANTABLE
- m_szColumnName
- m_szTableCatalog
- m_szGrantor
- GRANTOR
- GRANTEE
- COLUMN_PROPID
- m_guidColumn
- COLUMN_PRIVILEGES
- m_szTableName
- CColumnPrivilegeInfo
- m_szGrantee
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_PROPID
- GRANTOR
- m_szPrivilegeType
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- COLUMN_PRIVILEGES
- IS_GRANTABLE
- m_nColumnPropID
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szTableCatalog
- m_szGrantee
- m_szGrantor
- m_szTableName
- CColumnPrivileges typedef class
- COLUMN_GUID
- GRANTEE
- m_guidColumn
- CColumnPrivilegeInfo parameter class
- m_bIsGrantable
ms.assetid: 245df365-421f-43c6-9fcd-fb2197c871c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7595d0f945744804b91a62ecfd41c5d2f3d9b165
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ccolumnprivileges-ccolumnprivilegeinfo"></a>CColumnPrivileges, CColumnPrivilegeInfo
Rufen Sie die-typedefklasse **CColumnPrivileges** zum Implementieren der Parameterklasse **CColumnPrivilegeInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse gibt die Berechtigungen für Spalten von Tabellen, in dem Katalog definiert, die verfügbar sind oder von einem angegebenen Benutzer gewährt werden.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [COLUMN_PRIVILEGES-Rowset](https://msdn.microsoft.com/en-us/library/ms715800.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szGrantor|GRANTOR|  
|m_szGrantee|GRANTEE|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_szPrivilegeType|PRIVILEGE_TYPE|  
|m_bIsGrantable|IS_GRANTABLE|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbsch.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)