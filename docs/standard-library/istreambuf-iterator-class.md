---
title: "istreambuf_iterator-Klasse"
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
  - "istreambuf_iterator"
  - "std.istreambuf_iterator"
  - "std::istreambuf_iterator"
  - "streambuf/std::istreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istreambuf_iterator-Klasse"
ms.assetid: 39002da2-61a6-48a5-9d0c-5df8271f6038
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# istreambuf_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse istreambuf\_iterator beschreibt ein Eingabeiteratorobjekt, das Zeichenelemente aus einem Eingabestreampuffer extrahiert, auf den es durch ein gespeichertes Objekt des Typs Zeiger auf `basic_streambuf`\<**CharType**, **Traits**\> zugreift.  
  
## Syntax  
  
```  
  
      template <   
   class CharType  
   class Traits = char_traits<CharType>  
>  
class istreambuf_iterator  
: public iterator<input_iterator_tag, CharType, typename Traits::off_type, CharType *, CharType&>  
```  
  
#### Parameter  
 `CharType`  
 Der Typ, der den Zeichentyp für das istreambuf\_iterator\-Objekt darstellt.  
  
 `Traits`  
 Der Typ, der den Zeichentyp für das istreambuf\_iterator\-Objekt darstellt.  Dieses Argument ist optional, und der Standardwert ist `char_traits`\<*CharType\>.*  
  
## Hinweise  
 Die istreambuf\_iterator\-Klasse muss den Anforderungen für einen Eingabeiterator erfüllen.  
  
 Nachdem ein Objekt der istreambuf\_iterator\-Klasse mit einem als nicht NULL gespeicherten Zeiger erstellt oder erhöht hat, versucht das Objekt effektiv, ein Objekt vom Typ **CharType** aus dem zugeordneten Eingabestream zu extrahieren und zu speichern.  Die Extraktion kann jedoch verzögert werden, bis das Objekt tatsächlich dereferenziert oder kopiert wurde.  Wenn die Extraktion fehlschlägt, ersetzt das Objekt den gespeicherten Zeiger durch einen NULL\-Zeiger und erstellt so einen Indikator für das Ende der Sequenz.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[istreambuf\_iterator](../Topic/istreambuf_iterator::istreambuf_iterator.md)|Erstellt ein `istreambuf_iterator`\-Objekt, das initialisiert wird, um Zeichen aus dem Eingabestream zu lesen.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/istreambuf_iterator::char_type.md)|Ein Typ, der für den Zeichentyp von `ostreambuf_iterator` bereitgestellt wird.|  
|[int\_type](../Topic/istreambuf_iterator::int_type.md)|Ein Typ, der einen Ganzzahltyp für ein `istreambuf_iterator`\-Objekt bereitstellt.|  
|[istream\_type](../Topic/istreambuf_iterator::istream_type.md)|Ein Typ, der für den Streamtyp von `istream_iterator` bereitgestellt wird.|  
|[streambuf\_type](../Topic/istreambuf_iterator::streambuf_type.md)|Ein Typ, der für den Streamtyp von `istreambuf_iterator` bereitgestellt wird.|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|Ein Typ, der für den Merkmaltyp von `istream_iterator` bereitgestellt wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[equal](../Topic/istreambuf_iterator::equal.md)|Testet zwei Eingabestreampufferiteratoren auf Gleichheit.|  
  
### Operators  
  
|||  
|-|-|  
|[operator\*](../Topic/istreambuf_iterator::operator*.md)|Der Dereferenzierungsoperator gibt das folgende Zeichen im Stream zurück.|  
|[operator\+\+](../Topic/istreambuf_iterator::operator++.md)|Gibt entweder das folgende Zeichen im Eingabestream zurück oder kopiert das Objekt vor dem Inkrementieren und gibt die Kopie zurück.|  
|[Operator\-\>](../Topic/istreambuf_iterator::operator-%3E.md)|Gibt den Wert eines Members zurück, falls vorhanden.|  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [iterator\-Struktur](../standard-library/iterator-struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)