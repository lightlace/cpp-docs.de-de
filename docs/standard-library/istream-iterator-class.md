---
title: "istream_iterator-Klasse"
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
  - "iterator/std::istream_iterator"
  - "std.istream_iterator"
  - "std::istream_iterator"
  - "istream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream_iterator-Klasse"
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: 18
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# istream_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Eingabeiteratorobjekt.  Es werden Objekte der Klasse `Type` aus einem Eingabestream extrahiert. Der Zugriff darauf erfolgt durch ein gespeichertes Objekt vom Typ `pointer` auf `basic_istream`\<`CharType`, `Traits`\>.  
  
## Syntax  
  
```  
template<class Type,  
    class CharType = char,  
    class Traits = char_traits<CharType>,  
    class Distance = ptrdiff_t,  
> class istream_iterator  
 : public iterator<  
        input_iterator_tag,  
        Type,   
        Distance,   
        const Type *,  
        const Type&  
    >;  
```  
  
#### Parameter  
 `Type`  
 Der Typ des Objekts, das aus dem Eingabestream extrahiert werden soll.  
  
 `CharType`  
 Der Typ, der den Zeichentyp für `istream_iterator` darstellt.  Dieses Argument ist optional, und der Standardwert ist `char`.  
  
 `Traits`  
 Der Typ, der den Zeichentyp für `istream_iterator` darstellt.  Dieses Argument ist optional, und der Standardwert ist `char_traits`\<`CharType`\>.  
  
 `Distance`  
 Ein ganzzahliger Typ mit Vorzeichen, der den Differenztyp für den `istream_iterator` darstellt.  Dieses Argument ist optional, und der Standardwert ist `ptrdiff_t`.  
  
 Nachdem ein Objekt der Klasse istream\_iterator mit einem ungleich NULL gespeicherten Zeiger erstellt oder erhöht wurde, versucht das Objekt, ein Objekt vom Typ `Type` aus dem zugewiesenen Eingabestream zu extrahieren und zu speichern.  Wenn die Extraktion fehlschlägt, ersetzt das Objekt den gespeicherten Zeiger durch einen NULL\-Zeiger und erstellt so einen Indikator für das Ende der Sequenz.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[istream\_iterator](../Topic/istream_iterator::istream_iterator.md)|Erstellt entweder einen End\-of\-Stream\-Iterator als Standard\-`istream_iterator` oder ein `istream_iterator`, der für den Streamtyp des Iterators initialisiert wird, von dem gelesen wird.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/istream_iterator::char_type.md)|Ein Typ, der für den Zeichentyp von `istream_iterator` bereitgestellt wird.|  
|[istream\_type](../Topic/istream_iterator::istream_type.md)|Ein Typ, der für den Streamtyp von `istream_iterator` bereitgestellt wird.|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|Ein Typ, der für den Merkmaltyp von `istream_iterator` bereitgestellt wird.|  
  
### Operators  
  
|||  
|-|-|  
|[operator\*](../Topic/istream_iterator::operator*.md)|Der Dereferenzierungsoperator gibt das gespeicherte Objekt vom Typ `Type` zurück, das vom `istream_iterator` adressiert wird.|  
|[Operator\-\>](../Topic/istream_iterator::operator-%3E.md)|Gibt den Wert eines Members zurück, falls vorhanden.|  
|[operator\+\+](../Topic/istream_iterator::operator++.md)|Extrahiert entweder ein inkrementiertes Objekt im Eingabestream oder kopiert das Objekt vor dem Inkrementieren und gibt die Kopie zurück.|  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [input\_iterator\_tag\-Struktur](../standard-library/input-iterator-tag-struct.md)   
 [iterator\-Struktur](../standard-library/iterator-struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)