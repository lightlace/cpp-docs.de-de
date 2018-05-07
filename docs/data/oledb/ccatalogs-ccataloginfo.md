---
title: CCatalogs, CCatalogInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCatalogs
- m_szName
- CCatalogInfo
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- CCatalogInfo parameter class
- CCatalogs typedef class
- m_szName
- m_szDescription
ms.assetid: 8362cbbd-2f00-4272-8518-fc235c4de193
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a62c0a95e057d3ffa96f59fc1c460de78c031550
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ccatalogs-ccataloginfo"></a>CCatalogs, CCatalogInfo
Rufen Sie die-typedefklasse **CCatalogs** zum Implementieren der Parameterklasse **CCatalogInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse gibt die physischen Attribute zugegriffen werden kann, aus dem DBMS Katalogen zugeordnet sind.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [Kataloge Rowset](https://msdn.microsoft.com/en-us/library/ms721241.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szName|CATALOG_NAME|  
|m_szDescription|DESCRIPTION|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atldbsch.h" Einfügen  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)