---
title: "tlbid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tlbid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tlbid-Attribut"
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# tlbid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Ermöglicht das Laden anderer Bibliotheken als der primären Typbibliothek.  
  
## Syntax  
  
```  
tlbid(number)  
```  
  
#### Parameter  
 `number`  
 Die Nummer der Typbibliothek in `filename`.  
  
## Hinweise  
 Wenn mehrere Typbibliotheken in einer DLL zusammengefasst sind, können mit `tlbid` andere Bibliotheken als die primäre Typbibliothek geladen werden.  
  
 Beispiel:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 identisch mit folgendem Ausdruck:  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)