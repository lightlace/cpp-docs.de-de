---
title: "allocator&lt;void&gt;-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::allocator<void>"
  - "std::allocator<void>"
  - "std.allocator<void>"
  - "allocator<void>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator<void>-Klasse"
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# allocator&lt;void&gt;-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Spezialisierung der Vorlagenklassen\-Zuweisung, um `void` einzugeben, die Typen definieren, die sinnvoll in diesem Kontext befinden.  
  
## Syntax  
  
```  
template<>  
   class allocator<void> {  
   typedef void *pointer;  
   typedef const void *const_pointer;  
   typedef void value_type;  
   template<class Other>  
      struct rebind;  
   allocator( );  
   allocator(  
      const allocator<void>&  
   );  
   template<class Other>  
      allocator(  
         const allocator<Other>&  
      );  
   template<class Other>  
      allocator<void>& operator=(  
         const allocator<Other>&  
      );  
   };  
```  
  
## Hinweise  
 Die Klasse explizit spezialisiert Vorlagenklasse [Zuweisung](../standard-library/allocator-class.md) für Typ *void.* Die Konstruktoren und Zuweisungsoperator verhalten sich genauso wie für die Vorlagenklasse, aber sie definiert nur die folgenden Typen:  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md).  
  
-   [Zeiger](../Topic/allocator::pointer.md).  
  
-   [value\_type](../Topic/allocator::value_type.md).  
  
-   [binden Sie erneut](../Topic/allocator::rebind.md), eine geschachtelte Vorlagenklasse.  
  
## Anforderungen  
 **Header:** \<Arbeitsspeicher\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)