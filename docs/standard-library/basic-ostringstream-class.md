---
title: "basic_ostringstream-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_ostringstream"
  - "std.basic_ostringstream"
  - "sstream/std::basic_ostringstream"
  - "std::basic_ostringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ostringstream-Klasse"
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# basic_ostringstream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc` steuert.  
  
## Syntax  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_ostringstream : public basic_ostream<Elem, Tr>  
```  
  
#### Parameter  
 `Alloc`  
 Die Zuweisungsklasse.  
  
 `Elem`  
 Der Typ des grundlegenden Elements der Zeichenfolge.  
  
 *Tr*  
 Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.  
  
## Hinweise  
 Die Klasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer steuert, der Elemente des Typs **Elem** enthält, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind und dessen Elemente durch eine Zuweisung der Klasse `Alloc` zugeordnet werden.  Das Objekt speichert ein aus der Klasse basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\> abgeleitetes Objekt.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_ostringstream](../Topic/basic_ostringstream::basic_ostringstream.md)|Konstruiert ein Objekt vom Typ `basic_ostringstream`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_ostringstream::allocator_type.md)|Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_ostringstream::rdbuf.md)|Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` zu [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<`Elem``Tr``Alloc`\> zurück.|  
|[str](../Topic/basic_ostringstream::str.md)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|  
  
## Anforderungen  
 **Header:** \<sstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)