---
title: "rename_search_namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rename_search_namespace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rename_search_namespace-Attribut"
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# rename_search_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Hat dieselbe Funktionalität wie das [rename\_namespace](../preprocessor/rename-namespace.md)\-Attribut, wird jedoch in Typbibliotheken verwendet, damit Sie die \#import\-Direktive mit dem [auto\_search](../preprocessor/auto-search.md)\-Attribut verwenden.  
  
## Syntax  
  
```  
rename_search_namespace("NewName")  
```  
  
#### Parameter  
 `NewName`  
 Der neue Name des neuen Namespace.  
  
## Hinweise  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)