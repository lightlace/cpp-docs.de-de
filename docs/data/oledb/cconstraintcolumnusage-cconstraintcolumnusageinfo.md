---
title: CConstraintColumnUsage, CConstraintColumnUsageInfo | Microsoft Docs
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
- m_szConstraintCatalog
- CConstraintColumnUsage
- m_nColumnPropID
- COLUMN_GUID
- CONSTRAINT_NAME
- m_szColumnName
- m_szTableCatalog
- m_szConstraintSchema
- COLUMN_PROPID
- m_guidColumn
- CONSTRAINT_COLUMN_USAGE
- m_szTableName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- CConstraintColumnUsageInfo
- m_szConstraintName
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_PROPID
- m_szConstraintCatalog
- CONSTRAINT_COLUMN_USAGE
- CONSTRAINT_CATALOG
- CConstraintColumnUsageInfo parameter class
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- CONSTRAINT_NAME
- CConstraintColumnUsage typedef class
- m_nColumnPropID
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szTableCatalog
- m_szConstraintName
- m_szTableName
- m_szConstraintSchema
- COLUMN_GUID
- m_guidColumn
ms.assetid: 7d4d94e8-2025-4fcc-a176-c9b231eca77b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e7d76c426ff203d989250832231db1783562948
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cconstraintcolumnusage-cconstraintcolumnusageinfo"></a>CConstraintColumnUsage, CConstraintColumnUsageInfo
Rufen Sie die-typedefklasse **CConstraintColumnUsage** zum Implementieren der Parameterklasse **CConstraintColumnUsageInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse identifiziert die Spalten, die von referenziellen Einschränkungen, unique-Einschränkungen, Check-Einschränkungen und Assertionen verwendet, die im Katalog definierten und Eigentümer ein angegebener Benutzer.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [CONSTRAINT_COLUMN_USAGE-Rowset](https://msdn.microsoft.com/en-us/library/ms724522.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_szConstraintCatalog|CONSTRAINT_CATALOG|  
|m_szConstraintSchema|CONSTRAINT_SCHEMA|  
|m_szConstraintName|CONSTRAINT_NAME|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbsch.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)