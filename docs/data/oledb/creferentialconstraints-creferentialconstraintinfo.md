---
title: CReferentialConstraints, CReferentialConstraintInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szUniqueName
- m_szCatalog
- DELETE_RULE
- m_szUniqueCatalog
- CONSTRAINT_NAME
- CReferentialConstraintInfo
- MATCH_OPTION
- m_szSchema
- m_szDeleteRule
- m_szUpdateRule
- m_szUniqueSchema
- CReferentialConstraints
- m_szName
- CONSTRAINT_CATALOG
- m_szMatchOption
- CONSTRAINT_SCHEMA
dev_langs:
- C++
helpviewer_keywords:
- m_szUniqueSchema
- DESCRIPTION class data member
- m_szSchema
- CONSTRAINT_CATALOG
- CReferentialConstraints typedef class
- m_szUniqueName
- m_szCatalog
- CONSTRAINT_NAME
- m_szDeleteRule
- DELETE_RULE
- MATCH_OPTION
- CONSTRAINT_SCHEMA
- m_szName
- m_szDescription
- m_szMatchOption
- m_szUniqueCatalog
- m_szUpdateRule
- CReferentialConstraintInfo parameter class
ms.assetid: 5d485358-be29-41c2-b0ce-19e023598e73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cb1a60994b286b68e9c381c9faa8718020739161
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creferentialconstraints-creferentialconstraintinfo"></a>CReferentialConstraints, CReferentialConstraintInfo
Rufen Sie die-typedefklasse **CReferentialConstraints** zum Implementieren der Parameterklasse **CReferentialConstraintInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse gibt die referenziellen Einschränkungen, in dem Katalog definiert, die von einem angegebenen Benutzer gehören.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [REFERENTIAL_CONSTRAINTS-Rowset](https://msdn.microsoft.com/en-us/library/ms719737.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szCatalog|CONSTRAINT_CATALOG|  
|m_szSchema|CONSTRAINT_SCHEMA|  
|m_szName|CONSTRAINT_NAME|  
|m_szUniqueCatalog|UNIQUE_CONSTRAINT_CATALOG|  
|m_szUniqueSchema|UNIQUE_CONSTRAINT_SCHEMA|  
|m_szUniqueName|UNIQUE_CONSTRAINT_NAME|  
|m_szMatchOption|MATCH_OPTION|  
|m_szUpdateRule|UPDATE_RULE|  
|m_szDeleteRule|DELETE_RULE|  
|m_szDescription|DESCRIPTION|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atldbsch.h" Einfügen  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)