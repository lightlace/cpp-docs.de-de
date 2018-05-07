---
title: CViews, CViewInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szTableSchema
- m_bCheckOption
- CViews
- CHECK_OPTION
- CViewInfo
- m_szTableCatalog
- IS_UPDATABLE
- m_szDefinition
- m_szTableName
- m_bIsUpdatable
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- CHECK_OPTION
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- m_bCheckOption
- TABLE_SCHEMA
- m_szTableCatalog
- m_szDescription
- m_szDefinition
- m_szTableName
- CViewInfo parameter class
- m_bIsUpdatable
- IS_UPDATABLE
- CViews typedef class
ms.assetid: ad864181-4fab-4919-b0fd-45df5da230d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b17df30dac07222f026f23f778a201cc5824d72a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cviews-cviewinfo"></a>CViews, CViewInfo
Rufen Sie die-typedefklasse **CViews** zum Implementieren der Parameterklasse **CViewInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse gibt die Tabellen auf, die im Katalog definierten Tabellen angezeigt, und Eigentümer ein angegebener Benutzer abhängig sind.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [Ansichten Rowset](https://msdn.microsoft.com/en-us/library/ms723122.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szDefinition|VIEW_DEFINITION|  
|m_bCheckOption|CHECK_OPTION|  
|m_bIsUpdatable|IS_UPDATABLE|  
|m_szDescription|DESCRIPTION|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atldbsch.h" Einfügen  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)