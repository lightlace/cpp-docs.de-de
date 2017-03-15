---
title: "high_property_prefixes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "high_property_prefixes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "high_property_prefixes-Attribut"
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
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