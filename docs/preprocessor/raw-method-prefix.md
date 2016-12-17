---
title: "raw_method_prefix"
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
  - "raw_method_prefix"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "raw_method_prefix-Attribut"
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# raw_method_prefix
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Gibt ein anderes Präfix an, um Namenskonflikte zu vermeiden.  
  
## Syntax  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### Parameter  
 `Prefix`  
 Das zu verwendende Präfix.  
  
## Hinweise  
 Eigenschaften und Methoden auf niedriger Ebene werden von Memberfunktionen verfügbar gemacht, deren Name das Standardpräfix **raw\_** verwendet, um Namenskonflikte mit Memberfunktionen zur Fehlerbehandlung auf hoher Ebene zu vermeiden.  
  
> [!NOTE]
>  Die Auswirkungen des `raw_method_prefix`\-Attributs werden durch das Vorhandensein des [raw\_interfaces\_only](#_predir_raw_interfaces_only)\-Attributs nicht geändert.  `raw_method_prefix` hat beim Angeben eines Präfix immer Vorrang vor `raw_interfaces_only`.  Wenn beide Attribute in derselben `#import`\-Anweisung verwendet werden, wird das Präfix verwendet, das vom `raw_method_prefix`\-Attribut angegeben wird.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)