---
title: "ostream_iterator-Klasse"
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
  - "ostream_iterator"
  - "std.ostream_iterator"
  - "std::ostream_iterator"
  - "iterator/std::ostream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream_iterator-Klasse"
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
caps.latest.revision: 17
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# ostream_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse ostream\_iterator beschreibt ein Ausgabeiteratorobjekt, das aufeinander folgende Elemente in den Ausgabestream mit der Extraktion **operator \<\<** schreibt.  
  
## Syntax  
  
```  
  
      template <  
   class Type   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
class ostream_iterator  
```  
  
#### Parameter  
 *Typ*  
 Der Typ des in den Ausgabestream einzufügenden Objekts.  
  
 `CharType`  
 Der Typ, der den Zeichentyp für `ostream_iterator` darstellt.  Dieses Argument ist optional, und der Standardwert ist `char`*.*  
  
 `Traits`  
 Der Typ, der den Zeichentyp für `ostream_iterator` darstellt.  Dieses Argument ist optional, und der Standardwert ist `char_traits`\<*CharType\>.*  
  
 Die ostream\_iterator\-Klasse muss den Anforderungen für einen Ausgabeiterator entsprechen.  Algorithmen können mit `ostream_iterator` direkt in Ausgabestreams geschrieben werden.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[ostream\_iterator](../Topic/ostream_iterator::ostream_iterator.md)|Erstellt einen `ostream_iterator`, der initialisiert und zum Schreiben in den Ausgabestream begrenzt wird.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/ostream_iterator::char_type.md)|Ein Typ, der für den Zeichentyp von `ostream_iterator` bereitgestellt wird.|  
|[ostream\_type](../Topic/ostream_iterator::ostream_type.md)|Ein Typ, der für den Streamtyp von `ostream_iterator` bereitgestellt wird.|  
|[traits\_type](../Topic/ostream_iterator::traits_type.md)|Ein Typ, der für den Merkmaltyp von `ostream_iterator` bereitgestellt wird.|  
  
### Operators  
  
|||  
|-|-|  
|[operator\*](../Topic/ostream_iterator::operator*.md)|Der Dereferenzierungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks \*`i` \= `x` verwendet wird.|  
|[operator\+\+](../Topic/ostream_iterator::operator++.md)|Ein nicht funktionaler Inkrementoperator, der einen `ostream_iterator` zum gleichen Objekt zurückgibt, das er adressiert hat, bevor der Vorgang aufgerufen wurde.|  
|[operator\=](../Topic/ostream_iterator::operator=.md)|Ein Zuweisungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks \*`i` \= `x` zum Schreiben in einen Ausgabestream verwendet wird.|  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<iterator\>](../standard-library/iterator.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)