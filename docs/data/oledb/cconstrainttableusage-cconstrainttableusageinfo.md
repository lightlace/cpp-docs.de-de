---
title: CConstraintTableUsage, CConstraintTableUsageInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CConstraintTableUsageInfo
- CONSTRAINT_TABLE_USAGE
- m_szTableSchema
- m_szConstraintCatalog
- CONSTRAINT_NAME
- m_szTableCatalog
- m_szConstraintSchema
- m_szTableName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- CConstraintTableUsage
- m_szConstraintName
dev_langs:
- C++
helpviewer_keywords:
- CConstraintTableUsage typedef class
- m_szConstraintCatalog
- CONSTRAINT_CATALOG
- m_szTableSchema
- CConstraintTableUsageInfo parameter class
- TABLE_CATALOG
- CONSTRAINT_TABLE_USAGE
- TABLE_NAME
- CONSTRAINT_NAME
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szTableCatalog
- m_szConstraintName
- m_szTableName
- m_szConstraintSchema
ms.assetid: 666b44de-3922-4c5e-ad17-d5ea27120174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7662cc111101d63729b5cb37512988edd61ead14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cconstrainttableusage-cconstrainttableusageinfo"></a>CConstraintTableUsage, CConstraintTableUsageInfo
Rufen Sie die-typedefklasse **CConstraintTableUsage** zum Implementieren der Parameterklasse **CConstraintTableUsageInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse identifiziert die Tabellen, die von referenziellen Einschränkungen, unique-Einschränkungen, Check-Einschränkungen und Assertionen verwendet, die im Katalog definierten und Eigentümer ein angegebener Benutzer.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [CONSTRAINT_TABLE_USAGE-Rowset](https://msdn.microsoft.com/en-us/library/ms724522.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szConstraintCatalog|CONSTRAINT_CATALOG|  
|m_szConstraintSchema|CONSTRAINT_SCHEMA|  
|m_szConstraintName|CONSTRAINT_NAME|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atldbsch.h" Einfügen  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)