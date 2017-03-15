---
title: "raw_method_prefix | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_method_prefix"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_method_prefix-Attribut"
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
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