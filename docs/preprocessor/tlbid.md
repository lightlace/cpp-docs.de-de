---
title: "tlbid"
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
  - "tlbid"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tlbid-Attribut"
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
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