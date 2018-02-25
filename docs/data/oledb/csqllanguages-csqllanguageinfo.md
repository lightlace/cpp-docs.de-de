---
title: CSQLLanguages, CSQLLanguageInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSQLLanguageInfo
- m_szProgrammingLanguage
- m_szImplementation
- m_szIntegrity
- m_szBindingStyle
- m_szConformance
- m_szSource
- m_szYear
- CSQLLanguages
dev_langs:
- C++
helpviewer_keywords:
- m_szBindingStyle
- m_szProgrammingLanguage
- m_szYear
- m_szImplementation
- m_szSource
- m_szConformance
- CSQLLanguages typedef class
- CSQLLanguageInfo parameter class
- m_szIntegrity
ms.assetid: 9c36c5bb-6917-49c3-9ac3-942339893f19
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: effac49070d5c3498f57ceade738b353c86c85c7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="csqllanguages-csqllanguageinfo"></a>CSQLLanguages, CSQLLanguageInfo
Rufen Sie die-typedefklasse **CSQLLanguages** zum Implementieren der Parameterklasse **CSQLLanguageInfo**.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) für Weitere Informationen zur Verwendung von typedef-Klassen.  
  
 Diese Klasse gibt die Übereinstimmungsebenen, Optionen und Dialekte von der SQL-Implementierung Verarbeitung von Daten im Katalog definierten unterstützt.  
  
 Die folgende Tabelle enthält die Datenmember der Klasse und ihre entsprechenden OLE DB-Spalten. Finden Sie unter [SQL_LANGUAGES-Rowset](https://msdn.microsoft.com/en-us/library/ms714374.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen über das Schema und die Spalten.  
  
|Datenmember|OLE DB-Spalten|  
|------------------|--------------------|  
|m_szSource|SQL_LANGUAGE_SOURCE|  
|m_szYear|SQL_LANGUAGE_YEAR|  
|m_szConformance|SQL_LANGUAGE_CONFORMANCE|  
|m_szIntegrity|SQL_LANGUAGE_INTEGRITY|  
|m_szImplementation|SQL_LANGUAGE_IMPLEMENTATION|  
|m_szBindingStyle|SQL_LANGUAGE_BINDING_STYLE|  
|m_szProgrammingLanguage|SQL_LANGUAGE_PROGRAMMING_LANGUAGE|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbsch.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRestrictions-Klasse](../../data/oledb/crestrictions-class.md)