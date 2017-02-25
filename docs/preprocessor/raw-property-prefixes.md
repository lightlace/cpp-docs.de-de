---
title: "raw_property_prefixes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_property_prefixes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_property_prefixes-Attribut"
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# raw_property_prefixes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Gibt alternative Präfixe für drei Eigenschaftenmethoden an.  
  
## Syntax  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### Parameter  
 `GetPrefix`  
 Für die **propget**\-Methoden zu verwendendes Präfix.  
  
 `PutPrefix`  
 Für die **propput**\-Methoden zu verwendendes Präfix.  
  
 `PutRefPrefix`  
 Für die **propputref**\-Methoden zu verwendendes Präfix.  
  
## Hinweise  
 Standardmäßig werden **propget**\-, **propput**\- und **propputref**\-Methoden auf niedriger Ebene durch Memberfunktionen verfügbar gemacht, die Namen mit Präfixen von **get\_**, **put\_** bzw. **putref\_** tragen.  Diese Präfixe sind kompatibel mit den Namen, die in den Headerdateien verwendet werden, die von MIDL generiert werden.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)