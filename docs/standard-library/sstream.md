---
title: "&lt;sstream&gt;"
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
  - "std.<sstream>"
  - "std::<sstream>"
  - "<sstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sstream-Header"
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
caps.latest.revision: 20
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# &lt;sstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert einige Vorlagenklassen, die iostreams Vorgänge auf den Sequenzen unterstützen, die in einem zugeordneten Objekt gespeichert werden.  Solche Sequenzen werden einfach nach und Objekten der Vorlagenklasse [basic\_string](../standard-library/basic-string-class.md).  
  
## Syntax  
  
```  
namespace std {  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringbuf;  
typedef basic_stringbuf<char> stringbuf;  
typedef basic_stringbuf<wchar_t> wstringbuf;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_istringstream;  
typedef basic_istringstream<char> istringstream;  
typedef basic_istringstream<wchar_t> wistringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_ostringstream;  
typedef basic_ostringstream<char> ostringstream;  
typedef basic_ostringstream<wchar_t> wostringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringstream;  
typedef basic_stringstream<char> stringstream;  
typedef basic_stringstream<wchar_t> wstringstream;  
  
        // TEMPLATE FUNCTIONS  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_stringbuf<CharType, Traits, Allocator>& _Left,  
        basic_stringbuf<CharType, Traits, Allocator>& _Right  
    );   
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_istringstream<CharType, Traits, Allocator>& _Left,  
        basic_istringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_ostringstream<CharType, Traits, Allocator>& _Left,  
        basic_ostringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap (  
        basic_stringstream<CharType, Traits, Allocator>& _Left,  
        basic_stringstream<CharType, Traits, Allocator>& _Right  
    );  
}  // namespace std  
  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`_Left`|Verweis auf ein `sstream`\-Objekt.|  
|`_Right`|Verweis auf ein `sstream`\-Objekt.|  
  
## Hinweise  
 Objekte des Typs `char *` können die Funktionen in [\<strstream\>](../standard-library/strstream.md) zum Streamen verwenden.  `<strstream>` wird jedoch veraltet und `<sstream>` wird empfohlen.  
  
### Typedefs  
  
|||  
|-|-|  
|[istringstream](../Topic/istringstream.md)|Erstellt den Typ `basic_istringstream`, das auf einem `char` Vorlagenparameter spezialisiert ist.|  
|[ostringstream](../Topic/ostringstream.md)|Erstellt den Typ `basic_ostringstream`, das auf einem `char` Vorlagenparameter spezialisiert ist.|  
|[stringbuf](../Topic/stringbuf.md)|Erstellt den Typ `basic_stringbuf`, das auf einem `char` Vorlagenparameter spezialisiert ist.|  
|[stringstream](../Topic/stringstream.md)|Erstellt den Typ `basic_stringstream`, das auf einem `char` Vorlagenparameter spezialisiert ist.|  
|[wistringstream](../Topic/wistringstream.md)|Erstellt den Typ `basic_istringstream`, das auf einem `wchar_t` Vorlagenparameter spezialisiert ist.|  
|[wostringstream](../Topic/wostringstream.md)|Erstellt den Typ `basic_ostringstream`, das auf einem `wchar_t` Vorlagenparameter spezialisiert ist.|  
|[wstringbuf](../Topic/wstringbuf.md)|Erstellt den Typ `basic_stringbuf`, das auf einem `wchar_t` Vorlagenparameter spezialisiert ist.|  
|[wstringstream](../Topic/wstringstream.md)|Erstellt den Typ `basic_stringstream`, das auf einem `wchar_t` Vorlagenparameter spezialisiert ist.|  
  
### Manipulatoren  
  
|||  
|-|-|  
|[swap](../Topic/%3Csstream%3E%20swap.md)|Vertauscht die Werte zwischen zwei `sstream`\-Objekten aus.|  
  
### Klassen  
  
|||  
|-|-|  
|[basic\_stringbuf](../standard-library/basic-stringbuf-class.md)|Beschreibt einen Streampuffer, der die Übertragung von Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** festgelegt werden, und von einer Sequenz von Elementen, die in einem \- Objekt gespeichert wird.|  
|[basic\_istringstream](../standard-library/basic-istringstream-class.md)|Beschreibt ein Objekt, das von Extraktions\- Elementen und kodierter Objekte eines Streampuffer der Klasse [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, mit Elementen des Typs **Elem**\- Steuerelemente, deren Zeichenmerkmale durch die Klasse **Tr** festgelegt werden und deren Elemente einer Zuweisung der Klasse `Alloc` zugeordnet werden.|  
|[basic\_ostringstream](../standard-library/basic-ostringstream-class.md)|Beschreibt ein Objekt, das Einfügen von Elementen und kodierter Objekten in einen Streampuffer der Klasse [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, mit Elementen des Typs **Elem**\- Steuerelemente, deren Zeichenmerkmale durch die Klasse **Tr** festgelegt werden und deren Elemente einer Zuweisung der Klasse `Alloc` zugeordnet werden.|  
|[basic\_stringstream](../standard-library/basic-stringstream-class.md)|Beschreibt ein Objekt, das Einfügen und Suche von Elementen und kodierter Objekten mithilfe eines Streampuffers der Klasse [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, mit Elementen des Typs **Elem**\- Steuerelemente, deren Zeichenmerkmale durch die Klasse **Tr** festgelegt werden und deren Elemente einer Zuweisung der Klasse `Alloc` zugeordnet werden.|  
  
## Anforderungen  
  
-   **Header:** \<sstream\>  
  
-   **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)