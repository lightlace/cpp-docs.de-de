---
title: "high_property_prefixes"
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
  - "high_property_prefixes"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "high_property_prefixes-Attribut"
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# high_property_prefixes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Gibt alternative Präfixe für drei Eigenschaftenmethoden an.  
  
## Syntax  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### Parameter  
 `GetPrefix`  
 Für die **propget**\-Methoden zu verwendendes Präfix.  
  
 `PutPrefix`  
 Für die **propput**\-Methoden zu verwendendes Präfix.  
  
 `PutRefPrefix`  
 Für die **propputref**\-Methoden zu verwendendes Präfix.  
  
## Hinweise  
 Standardmäßig werden **propget**\-, **propput**\- und **propputref**\-Methoden für die Fehlerbehandlung auf hoher Ebene über die Memberfunktionen verfügbar gemacht, die Namen mit den Präfixen **Get**, `Put` bzw. **PutRef** tragen.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)