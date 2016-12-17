---
title: "no_namespace"
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
  - "no_namespace"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_namespace-Attribut"
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# no_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Gibt an, dass der Name des Namespaces nicht vom Compiler generiert wird.  
  
## Syntax  
  
```  
no_namespace  
```  
  
## Hinweise  
 Der Inhalt der Typbibliothek in der `#import`\-Headerdatei wird normalerweise in einem Namespace definiert.  Der Namespace\-Name wird in der **library**\-Anweisung der ursprünglichen IDL\-Datei angegeben.  Wenn das `no_namespace`\-Attribut angegeben ist, wird dieser Namespace nicht vom Compiler generiert.  
  
 Wenn Sie einen anderen Namespacenamen verwenden möchten, verwenden Sie stattdessen das [rename\_namespace](../preprocessor/rename-namespace.md)\-Attribut.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)