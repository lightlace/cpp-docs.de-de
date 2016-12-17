---
title: "ostreambuf_iterator-Klasse"
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
  - "std.ostreambuf_iterator"
  - "streambuf/std::ostreambuf_iterator"
  - "ostreambuf_iterator"
  - "std::ostreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostreambuf_iterator-Klasse"
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 16
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# ostreambuf_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse ostreambuf\_iterator beschreibt ein Ausgabeiteratorobjekt, das aufeinander folgende Zeichenelemente in den Ausgabestream mit der Extraktion **operator\>\>** schreibt.  Die `ostreambuf_iterator`\-Objekte unterscheiden sich von denen der [ostream\_iterator\-Klasse](../standard-library/ostream-iterator-class.md) insofern, als sie über Zeichen anstelle eines generischen Typs im Hinblick auf den Objekttyp verfügen, der in den Ausgabestream eingefügt wird.  
  
## Syntax  
  
```  
  
      template <   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
```  
  
#### Parameter  
 `CharType`  
 Der Typ, der den Zeichentyp für das ostreambuf\_iterator\-Objekt darstellt.  Dieses Argument ist optional, und der Standardwert ist `char`*.*  
  
 `Traits`  
 Der Typ, der den Zeichentyp für das ostreambuf\_iterator\-Objekt darstellt.  Dieses Argument ist optional, und der Standardwert ist `char_traits`\<*CharType\>.*  
  
## Hinweise  
 Die ostreambuf\_iterator\-Klasse muss den Anforderungen für einen Ausgabeiterator entsprechen.  Algorithmen können mit `ostreambuf_iterator` direkt in Ausgabestreams geschrieben werden.  Die Klasse bietet einen Streamiterator auf niedriger Ebene, der Zugriff auf den unformatierten E\/A\-Stream in Form von Zeichen und die Fähigkeit erlaubt, die Pufferung und die Zeichenumsetzungen zu umgehen, die mit den Streamiteratoren auf hoher Ebene verbunden sind.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[ostreambuf\_iterator](../Topic/ostreambuf_iterator::ostreambuf_iterator.md)|Erstellt einen `ostreambuf_iterator`, der zum Schreiben von Zeichen in den Ausgabestream initialisiert wird.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/ostreambuf_iterator::char_type.md)|Ein Typ, der für den Zeichentyp von `ostreambuf_iterator` bereitgestellt wird.|  
|[ostream\_type](../Topic/ostreambuf_iterator::ostream_type.md)|Ein Typ, der für den Streamtyp von `ostream_iterator` bereitgestellt wird.|  
|[streambuf\_type](../Topic/ostreambuf_iterator::streambuf_type.md)|Ein Typ, der für den Streamtyp von `ostreambuf_iterator` bereitgestellt wird.|  
|[traits\_type](../Topic/ostreambuf_iterator::traits_type.md)|Ein Typ, der für den Merkmaltyp von `ostream_iterator` bereitgestellt wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Fehler](../Topic/ostreambuf_iterator::failed.md)|Testet eine Einfügung in den Ausgabestreampuffer auf Fehler.|  
  
### Operators  
  
|||  
|-|-|  
|[operator\*](../Topic/ostreambuf_iterator::operator*.md)|Der Dereferenzierungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks \*`i` \= `x` verwendet wird.|  
|[operator\+\+](../Topic/ostreambuf_iterator::operator++.md)|Ein nicht funktionaler Inkrementoperator, der einen `ostreambuf_iterator` zum gleichen Objekt zurückgibt, das er adressiert hat, bevor der Vorgang aufgerufen wurde.|  
|[operator\=](../Topic/ostreambuf_iterator::operator=.md)|Der Operator fügt ein Zeichen in den zugeordneten Streampuffer ein.|  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<iterator\>](../standard-library/iterator.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)