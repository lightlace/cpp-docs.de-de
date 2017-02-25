---
title: "CSQLLanguages, CSQLLanguageInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSQLLanguageInfo"
  - "m_szProgrammingLanguage"
  - "m_szImplementation"
  - "m_szIntegrity"
  - "m_szBindingStyle"
  - "m_szConformance"
  - "m_szSource"
  - "m_szYear"
  - "CSQLLanguages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSQLLanguageInfo-Parameterklasse"
  - "CSQLLanguages-Typedefklasse"
  - "m_szBindingStyle"
  - "m_szConformance"
  - "m_szImplementation"
  - "m_szIntegrity"
  - "m_szProgrammingLanguage"
  - "m_szSource"
  - "m_szYear"
ms.assetid: 9c36c5bb-6917-49c3-9ac3-942339893f19
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CSQLLanguages, CSQLLanguageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rufen Sie die typedef\-Klasse **CSQLLanguages** auf, um dessen Parameterklasse **CSQLLanguageInfo** zu implementieren.  
  
## Hinweise  
 Siehe [Schemarowset\-Klassen und typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) weitere Informationen zur Verwendung von Informationen.  
  
 Diese Klasse identifiziert die Übereinstimmungsebenen, Optionen und \-dialekte, die von der SQL\-Implementierung die Daten Verarbeitung unterstützt werden, die im Katalog definiert werden.  
  
 Die folgende Tabelle zeigt die Klassendatenmember und ihre entsprechenden OLE DB Spalten auf.  Siehe [SQL\_LANGUAGES\-Rowset](https://msdn.microsoft.com/en-us/library/ms714374.aspx) in *der OLE DB\-Programmierreferenz* weitere Informationen über das Schema und Spalten.  
  
|Datenmember|OLE DB\-Spalten|  
|-----------------|---------------------|  
|m\_szSource|SQL\_LANGUAGE\_SOURCE|  
|m\_szYear|SQL\_LANGUAGE\_YEAR|  
|m\_szConformance|SQL\_LANGUAGE\_CONFORMANCE|  
|m\_szIntegrity|SQL\_LANGUAGE\_INTEGRITY|  
|m\_szImplementation|SQL\_LANGUAGE\_IMPLEMENTATION|  
|m\_szBindingStyle|SQL\_LANGUAGE\_BINDING\_STYLE|  
|m\_szProgrammingLanguage|SQL\_LANGUAGE\_PROGRAMMING\_LANGUAGE|  
  
## Voraussetzungen  
 **Header:**  atldbsch.h  
  
## Siehe auch  
 [CRestrictions\-Klasse](../../data/oledb/crestrictions-class.md)