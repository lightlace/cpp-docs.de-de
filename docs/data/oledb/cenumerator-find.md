---
title: "CEnumerator::Find | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CEnumerator::Find"
  - "ATL::CEnumerator::Find"
  - "ATL.CEnumerator.Find"
  - "CEnumerator.Find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Find-Methode"
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CEnumerator::Find
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sucht nach einen angegebenen Namen mit verfügbaren Anbieter.  
  
## Syntax  
  
```  
  
      bool Find(   
   TCHAR* szSearchName    
) throw( );  
```  
  
#### Parameter  
 *szSearchName*  
 \[in\] der zu suchenden Name.  
  
## Rückgabewert  
 **true**, wenn der Name gefunden wurde.  Andernfalls **false**.  
  
## Hinweise  
 Dieser **SOURCES\_NAME** den Namen Member [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) schließen an.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CEnumerator\-Klasse](../../data/oledb/cenumerator-class.md)