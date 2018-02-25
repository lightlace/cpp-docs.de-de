---
title: CCatalogs, CCatalogInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d08f384e29399e1f244595088c5b1cbda249138
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
 **Header:** atldbsch.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)