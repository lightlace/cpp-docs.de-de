---
title: "CTranslations, CTranslationInfo"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "m_szCatalog"
  - "m_szSourceCatalog"
  - "m_szTargetSchema"
  - "m_szTargetCatalog"
  - "m_szTargetName"
  - "CTranslationInfo"
  - "m_szSourceName"
  - "m_szSchema"
  - "CTranslations"
  - "m_szName"
  - "m_szSourceSchema"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTranslationInfo-Parameterklasse"
  - "CTranslations-Typedefklasse"
  - "m_szCatalog"
  - "m_szName"
  - "m_szSchema"
  - "m_szSourceCatalog"
  - "m_szSourceName"
  - "m_szSourceSchema"
  - "m_szTargetCatalog"
  - "m_szTargetName"
  - "m_szTargetSchema"
ms.assetid: 19a64828-2d4c-42a0-8bfb-b010e334a9b3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CTranslations, CTranslationInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rufen Sie die typedef\-Klasse **CTranslations** auf, um dessen Parameterklasse **CTranslationInfo** zu implementieren.  
  
## Hinweise  
 Siehe [Schemarowset\-Klassen und typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) weitere Informationen zur Verwendung von Informationen.  
  
 Diese Klasse identifiziert die Zeichenumsetzungen im Katalog, die definiert werden, die für einen spezifischen Benutzer zugänglich sind.  
  
 Die folgende Tabelle zeigt die Klassendatenmember und ihre entsprechenden OLE DB Spalten auf.  Siehe [ÜBERSETZUNGEN Rowset](https://msdn.microsoft.com/en-us/library/ms725365.aspx) in *der OLE DB\-Programmierreferenz* weitere Informationen über das Schema und Spalten.  
  
|Datenmember|OLE DB\-Spalten|  
|-----------------|---------------------|  
|m\_szCatalog|TRANSLATION\_CATALOG|  
|m\_szSchema|TRANSLATION\_SCHEMA|  
|m\_szName|TRANSLATION\_NAME|  
|m\_szSourceCatalog|SOURCE\_CHARACTER\_SET\_CATALOG|  
|m\_szSourceSchema|SOURCE\_CHARACTER\_SET\_SCHEMA|  
|m\_szSourceName|SOURCE\_CHARACTER\_SET\_NAME|  
|m\_szTargetCatalog|TARGET\_CHARACTER\_SET\_CATALOG|  
|m\_szTargetSchema|TARGET\_CHARACTER\_SET\_SCHEMA|  
|m\_szTargetName|TARGET\_CHARACTER\_SET\_NAME|  
  
## Voraussetzungen  
 **Header:**  atldbsch.h  
  
## Siehe auch  
 [CatDB](../../top/visual-cpp-samples.md)   
 [CRestrictions\-Klasse](../../data/oledb/crestrictions-class.md)