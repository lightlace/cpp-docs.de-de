---
title: "rename_namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rename_namespace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rename_namespace-Attribut"
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# rename_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Benennt den Namespace, der die Inhalte der Typbibliothek enthält, um.  
  
## Syntax  
  
```  
rename_namespace("NewName")  
```  
  
#### Parameter  
 `NewName`  
 Der neue Name des neuen Namespace.  
  
## Hinweise  
 Es akzeptiert ein einzelnes Argument, *NewName*, das den neuen Namen für den Namespace angibt.  
  
 Um den Namespace zu entfernen, verwenden Sie stattdessen das [no\_namespace](../preprocessor/no-namespace.md)\-Attribut.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)