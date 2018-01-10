---
title: CUsagePrivileges, CUsagePrivilegeInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szObjectCatalog
- CUsagePrivilegeInfo
- m_bIsGrantable
- OBJECT_NAME
- m_szPrivilegeType
- OBJECT_SCHEMA
- IS_GRANTABLE
- CUsagePrivileges
- m_szGrantor
- GRANTOR
- GRANTEE
- m_szObjectSchema
- OBJECT_CATALOG
- m_szObjectType
- m_szObjectName
- m_szGrantee
- OBJECT_TYPE
dev_langs: C++
helpviewer_keywords:
- OBJECT_NAME
- GRANTOR
- OBJECT_CATALOG
- CUsagePrivileges typedef class
- m_szPrivilegeType
- OBJECT_SCHEMA
- m_szObjectSchema
- m_szObjectType
- IS_GRANTABLE
- OBJECT_TYPE
- CUsagePrivilegeInfo parameter class
- m_szGrantee
- m_szObjectCatalog
- m_szGrantor
- GRANTEE
- m_bIsGrantable
- m_szObjectName
ms.assetid: 09460e7f-3947-4837-ad1e-407b94acedb8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ae759b77aa5e95eda7334cea1357e8882667aba9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cusageprivileges-cusageprivilegeinfo"></a>CUsagePrivileges, CUsagePrivilegeInfo
Rufen Sie die-typedefklasse **CUsagePrivileges** zum Implementieren der Parameterklasse **CUsagePrivilegeInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse gibt die USAGE-Berechtigungen für Objekte, die im Katalog definierten, die für verfügbar sind oder von einem bestimmten Benutzer erteilten.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [USAGE_PRIVILEGES Rowset](https://msdn.microsoft.com/en-us/library/ms722743.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szGrantor|GRANTOR|  
|m_szGrantee|GRANTEE|  
|m_szObjectCatalog|OBJECT_CATALOG|  
|m_szObjectSchema|OBJECT_SCHEMA|  
|m_szObjectName|OBJECT_NAME|  
|m_szObjectType|OBJECT_TYPE|  
|m_szPrivilegeType|PRIVILEGE_TYPE|  
|m_bIsGrantable|IS_GRANTABLE|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atldbsch.h" Einfügen  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)