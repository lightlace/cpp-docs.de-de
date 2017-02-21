---
title: "forward_iterator_tag-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.forward_iterator_tag"
  - "forward_iterator_tag"
  - "std::forward_iterator_tag"
  - "xutility/std::forward_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_iterator_tag-Klasse"
  - "forward_iterator_tag-Struktur"
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# forward_iterator_tag-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, die einen Rückgabetyp für **iterator\_category**\-Funktion bereitstellt, die einen Vorwärtsiterator darstellt.  
  
## Syntax  
  
```  
  
   struct forward_iterator_tag  
: public input_iterator_tag {};  
```  
  
## Hinweise  
 Die Kategorientagklassen werden z kompilieren Tags für Algorithmus\-Auswahl verwendet.  Die Vorlagenfunktion muss herausgefunden, was die bestimmtste Kategorie des Iteratorarguments ist, dass es den effizientesten Algorithmus zur Kompilierungszeit verwenden kann.  Für jeden Iterator des Typs `Iterator`, muss `iterator_traits`\<**::iterator\_category**`Iterator`\>definiert werden, um das bestimmtste Kategorientag sein, das das Verhalten des Iterators beschreibt.  
  
 Der Typ ist der gleiche wie **Iterator**\<**Iter**\>**::iterator\_category**, wenn **Iter** ein Objekt beschrieben wird, das als Vorwärtsiterator dienen kann.  
  
## Beispiel  
 Siehe [iterator\_traits](../standard-library/iterator-traits-struct.md) oder [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) als Beispiel dafür, wie sich **iterator\_tag**s verwendet.  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [input\_iterator\_tag\-Struktur](../standard-library/input-iterator-tag-struct.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)