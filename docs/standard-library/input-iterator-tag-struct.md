---
title: "input_iterator_tag-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "input_iterator_tag"
  - "std.input_iterator_tag"
  - "std::input_iterator_tag"
  - "xutility/std::input_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "input_iterator_tag-Klasse"
  - "input_iterator_tag-Struktur"
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# input_iterator_tag-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, die einen Rückgabetyp für **iterator\_category**\-Funktion bereitstellt, die einen Eingabeiterator darstellt.  
  
## Syntax  
  
```  
  
struct input_iterator_tag {};  
  
```  
  
## Hinweise  
 Die Kategorientagklassen werden z kompilieren Tags für Algorithmus\-Auswahl verwendet.  Die Vorlagenfunktion muss die bestimmtste Kategorie des Iteratorarguments suchen, damit sie den effizientesten Algorithmus zur Kompilierungszeit verwenden kann.  Für jeden Iterator des Typs `Iterator`, muss `iterator_traits`\<**::iterator\_category**`Iterator`\>definiert werden, um das bestimmtste Kategorientag sein, das das Verhalten des Iterators beschreibt.  
  
 Der Typ ist der gleiche wie **Iterator**\<**Iter**\>**::iterator\_category**, wenn **Iter** ein Objekt beschrieben wird, das als Eingabeiterator dienen kann.  
  
## Beispiel  
 Siehe [iterator\_traits](../standard-library/iterator-traits-struct.md) oder [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) als Beispiel, wie **iterator\_tag**\- Blöcke. verwendet.  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)