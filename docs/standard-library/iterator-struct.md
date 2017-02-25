---
title: "iterator-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator"
  - "std::iterator"
  - "std.iterator"
  - "xutility/std::iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator-Klasse"
  - "iterator-Struktur"
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# iterator-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine niedrige leere Struktur verwendet, um sicherzustellen, dass eine benutzerdefinierte Iteratorklasse ordnungsgemäß mit **iterator\_trait**. S funktioniert.  
  
## Syntax  
  
```  
template<class Category, class Type, class Distance = ptrdiff_t  
    class Pointer = Type*, class Reference = Type&>  
    struct iterator {  
        typedef Category iterator_category;  
        typedef Type value_type;  
        typedef Distance difference_type;  
        typedef Distance distance_type;  
        typedef Pointer pointer;  
        typedef Reference reference;  
    };  
```  
  
## Hinweise  
 Die Vorlagenstruktur dient als Basistyp für alle Iteratoren.  Sie definiert die auszublendende Membertypen  
  
-   `iterator_category` \(ein Synonym für den Vorlagenparameter `Category`\).  
  
-   `value_type` \(ein Synonym für den Vorlagenparameter **Typ**\).  
  
-   `difference_type` \(ein Synonym für den Vorlagenparameter `Distance`\).  
  
-   `distance_type` \(ein Synonym für den Vorlagenparameter `Distance`\)  
  
-   `pointer` \(ein Synonym für den Vorlagenparameter `Pointer`\).  
  
-   `reference` \(ein Synonym für den Vorlagenparameter `Reference`\).  
  
 Beachten Sie, dass `value_type` keine Konstantentyp sein sollte, wenn **pointer** Punkte dargestellt ein Objekt von const **Typ** und von Verweis ein Objekt aus const **Typ**.  
  
## Beispiel  
 Unter [iterator\_traits](../standard-library/iterator-traits-struct.md) finden Sie ein Beispiel, wie Sie die Typen in der Iteratorbasisklasse deklariert und verwendet.  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<iterator\>](../standard-library/iterator.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)