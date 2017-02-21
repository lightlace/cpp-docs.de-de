---
title: "no_smart_pointers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_search_pointers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_smart_pointers-Attribut"
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# no_smart_pointers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Unterdrückt die Erstellung von intelligenten Zeigern für alle Schnittstellen in der Typbibliothek.  
  
## Syntax  
  
```  
no_smart_pointers  
```  
  
## Hinweise  
 Wenn Sie `#import` verwenden, rufen Sie standardmäßig die Deklaration eines intelligenten Zeigers für alle Schnittstellen in der Typbibliothek ab.  Diese intelligenten Zeiger sind vom Typ [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md).  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)