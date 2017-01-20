---
title: "output_iterator_tag-Struktur"
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
  - "std::output_iterator_tag"
  - "output_iterator_tag"
  - "xutility/std::output_iterator_tag"
  - "std.output_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "output_iterator_tag-Klasse"
  - "output_iterator_tag-Struktur"
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# output_iterator_tag-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, die einen Rückgabetyp für eine **iterator\_category**\-Funktion bereitstellt, die einen Output\-Iterator darstellt.  
  
## Syntax  
  
```  
  
struct output_iterator_tag {};  
  
```  
  
## Hinweise  
 Die Kategorie\-Tag\-Klassen werden verwendet, wie Tags für die Auswahl des Algorithmus zu kompilieren. Die Vorlagenfunktion muss die Kategorie des Arguments Iterator suchen, sodass es die effizienteste zum Zeitpunkt der Kompilierung verwendet werden kann. Für jede Iterator vom Typ `Iterator`, `iterator_traits`\<`Iterator`\>**:: Iterator\_category** muss definiert werden, um möglichst spezifische Kategorie\-Tag werden, die den Iterator Verhalten beschreibt.  
  
 Der Typ ist identisch mit **Iterator**\<**Iter**\>**:: Iterator\_category** Wenn **Iter** beschreibt ein Objekt, das als Output\-Iterator verwendet werden kann.  
  
 Dieses Tag ist nicht parametrisiert, auf die `value_type` oder `difference_type` für den Iterator wie bei anderen Iterator Tags, da Ausgabe Iteratoren nicht entweder eine `value_type` oder ein `difference_type`.  
  
## Beispiel  
 Finden Sie unter [Iterator\_traits](../standard-library/iterator-traits-struct.md) oder [Random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) ein Beispiel zum Verwenden von **Iterator\_tag**s.  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)