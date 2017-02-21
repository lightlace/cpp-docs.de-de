---
title: "basic_istringstream-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_istringstream"
  - "sstream/std::basic_istringstream"
  - "basic_istringstream"
  - "std.basic_istringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_istringstream-Klasse"
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# basic_istringstream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das die Extraktion von Elementen und codierten Objekten aus einem Streampuffer der Klasse [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\> steuert.  
  
## Syntax  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_istringstream : public basic_istream<Elem, Tr>  
```  
  
#### Parameter  
 `Alloc`  
 Die Zuweisungsklasse.  
  
 `Elem`  
 Der Typ des grundlegenden Elements der Zeichenfolge.  
  
 *Tr*  
 Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\> mit Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt und dessen Elemente durch eine Zuweisung der `Alloc`\-Klasse zugewiesen werden.  Das Objekt speichert ein aus der Klasse basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\> abgeleitetes Objekt.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_istringstream](../Topic/basic_istringstream::basic_istringstream.md)|Konstruiert ein Objekt vom Typ `basic_istringstream`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_istringstream::allocator_type.md)|Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_istringstream::rdbuf.md)|Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` zu [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<`Elem`, `Tr`, `Alloc`\> zurück.|  
|[str](../Topic/basic_istringstream::str.md)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|  
|[swap](../Topic/basic_istringstream::swap.md)|Tauscht die Werte in diesem `basic_istringstream`\-Objekt gegen die Werte im bereitgestellten Objekt.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_istringstream::operator=.md)|Weist die Werte aus dem Objektparameter diesem `basic_istringstream`\-Objekt zu.|  
  
## Anforderungen  
 **Header:** \<sstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)