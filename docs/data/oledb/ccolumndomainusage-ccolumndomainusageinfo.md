---
title: CColumnDomainUsage, CColumnDomainUsageInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szTableSchema
- m_szCatalog
- m_nColumnPropID
- CColumnDomainUsageInfo
- COLUMN_GUID
- DOMAIN_NAME
- m_szColumnName
- DOMAIN_SCHEMA
- DOMAIN_CATALOG
- m_szTableCatalog
- m_szSchema
- COLUMN_PROPID
- m_guidColumn
- CColumnDomainUsage
- m_szTableName
- m_szName
- COLUMN_DOMAIN_USAGE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_PROPID
- m_szSchema
- DOMAIN_NAME
- DOMAIN_SCHEMA
- m_szTableSchema
- TABLE_CATALOG
- m_szCatalog
- TABLE_NAME
- m_nColumnPropID
- CColumnDomainUsageInfo parameter class
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szName
- m_szTableCatalog
- m_szTableName
- COLUMN_DOMAIN_USAGE
- COLUMN_GUID
- CColumnDomainUsage typedef class
- m_guidColumn
- DOMAIN_CATALOG
ms.assetid: 5ff331f1-b99c-4002-9e04-367708c5759f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f0ca95cadf5ac3502ba8de034fad91a75ba123f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095270"
---
# <a name="ccolumndomainusage-ccolumndomainusageinfo"></a>CColumnDomainUsage, CColumnDomainUsageInfo
Rufen Sie die-typedefklasse **CColumnDomainUsage** zum Implementieren der Parameterklasse **CColumnDomainUsageInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse gibt die Spalten, in dem Katalog definiert, die einer Domäne im Katalog definierten und Eigentümer ein angegebener Benutzer abhängig sind.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [COLUMN_DOMAIN_USAGE-Rowset](https://msdn.microsoft.com/en-us/library/ms711240.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szCatalog|DOMAIN_CATALOG|  
|m_szSchema|DOMAIN_SCHEMA|  
|m_szName|DOMAIN_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atldbsch.h" Einfügen  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)