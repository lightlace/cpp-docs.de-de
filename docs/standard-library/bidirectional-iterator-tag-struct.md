---
title: "bidirectional_iterator_tag-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xutility/std::bidirectional_iterator_tag"
  - "std::bidirectional_iterator_tag"
  - "std.bidirectional_iterator_tag"
  - "bidirectional_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bidirectional_iterator_tag-Klasse"
  - "bidirectional_iterator_tag-Struktur"
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# bidirectional_iterator_tag-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, die einen Rückgabetyp für **iterator\_category**\-Funktion bereitstellt, die einen bidirektionalen Iterator darstellt.  
  
## Syntax  
  
```  
  
   struct bidirectional_iterator_tag  
: public forward_iterator_tag {};  
```  
  
## Hinweise  
 Die Kategorientagklassen werden z kompilieren Tags für Algorithmus\-Auswahl verwendet.  Die Vorlagenfunktion muss die bestimmtste Kategorie des Iteratorarguments suchen, damit sie den effizientesten Algorithmus zur Kompilierungszeit verwenden kann.  Für jeden Iterator des Typs `Iterator`, muss ::**iterator\_category**`iterator_traits`\<`Iterator`\>definiert werden, um das bestimmtste Kategorientag sein, das das Verhalten des Iterators beschreibt.  
  
 Der Typ ist der gleiche wie ::**iterator\_category** \>**Iterator**\<**Iter**, wenn **Iter** ein Objekt beschrieben wird, das als bidirektionalem Iterator dienen kann.  
  
## Beispiel  
 Unter [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) finden Sie ein Beispiel, wie `bidirectional_iterator_tag` verwendet.  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [forward\_iterator\_tag\-Struktur](../standard-library/forward-iterator-tag-struct.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)