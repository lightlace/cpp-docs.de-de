---
title: CTranslations, CTranslationInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szCatalog
- m_szSourceCatalog
- m_szTargetSchema
- m_szTargetCatalog
- m_szTargetName
- CTranslationInfo
- m_szSourceName
- m_szSchema
- CTranslations
- m_szName
- m_szSourceSchema
dev_langs: C++
helpviewer_keywords:
- m_szSourceSchema
- m_szSourceCatalog
- m_szSchema
- m_szTargetName
- m_szSourceName
- CTranslations typedef class
- m_szCatalog
- m_szTargetCatalog
- m_szName
- CTranslationInfo parameter class
- m_szTargetSchema
ms.assetid: 19a64828-2d4c-42a0-8bfb-b010e334a9b3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ee3acc16d5b0d39967960a0a78f4e0821edf90bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ctranslations-ctranslationinfo"></a>CTranslations, CTranslationInfo
Rufen Sie die-typedefklasse **CTranslations** zum Implementieren der Parameterklasse **CTranslationInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse gibt die im Katalog definierten Übersetzungen, die mit einem gegebenen Benutzer zugegriffen werden kann.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [ÜBERSETZUNGEN Rowset](https://msdn.microsoft.com/en-us/library/ms725365.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szCatalog|TRANSLATION_CATALOG|  
|m_szSchema|TRANSLATION_SCHEMA|  
|m_szName|TRANSLATION_NAME|  
|m_szSourceCatalog|SOURCE_CHARACTER_SET_CATALOG|  
|m_szSourceSchema|SOURCE_CHARACTER_SET_SCHEMA|  
|m_szSourceName|SOURCE_CHARACTER_SET_NAME|  
|m_szTargetCatalog|TARGET_CHARACTER_SET_CATALOG|  
|m_szTargetSchema|TARGET_CHARACTER_SET_SCHEMA|  
|m_szTargetName|TARGET_CHARACTER_SET_NAME|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atldbsch.h" Einfügen  
  
## <a name="see-also"></a>Siehe auch  
 [CatDB](../../visual-cpp-samples.md)   
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)