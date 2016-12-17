---
title: "basic_stringbuf-Klasse"
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
  - "basic_stringbuf"
  - "sstream/std::basic_stringbuf"
  - "std.basic_stringbuf"
  - "std::basic_stringbuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_stringbuf-Klasse"
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
caps.latest.revision: 28
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# basic_stringbuf-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen die Übertragung zu und aus einer Sequenz von in einem Arrayobjekt gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.  
  
## Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_stringbuf : public basic_streambuf<Elem, Tr>  
```  
  
#### Parameter  
 `Alloc`  
 Die Zuweisungsklasse.  
  
 `Elem`  
 Der Typ des grundlegenden Elements der Zeichenfolge.  
  
 `Tr`  
 Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.  
  
## Hinweise  
 Das Objekt wird reserviert, erweitert und freigegeben, sofern erforderlich, um Änderungen in der Sequenz zu berücksichtigen.  
  
 Ein Objekt der Klasse „basic\_stringbuf\<`Elem`, `Tr`, `Alloc`\>“ speichert eine Kopie des Arguments „`ios_base::`[openmode](../Topic/ios_base::openmode.md)“ aus seinem Konstruktor als sein `stringbuf`\-Modus **mode**:  
  
-   Wenn `mode & ios_base::in` ungleich 0 ist, kann auf den Eingabepuffer zugegriffen werden. Weitere Informationen finden Sie unter [basic\_streambuf\-Klasse](../standard-library/basic-streambuf-class.md).  
  
-   Wenn `mode & ios_base::out` ungleich 0 ist, kann auf den Ausgabepuffer zugegriffen werden.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_stringbuf](../Topic/basic_stringbuf::basic_stringbuf.md)|Konstruiert ein Objekt vom Typ `basic_stringbuf`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_stringbuf::allocator_type.md)|Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.|  
|[char\_type](../Topic/basic_stringbuf::char_type.md)|Verknüpft einen Typnamen mit dem `Elem`\-Vorlagenparameter.|  
|[int\_type](../Topic/basic_stringbuf::int_type.md)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[off\_type](../Topic/basic_stringbuf::off_type.md)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[pos\_type](../Topic/basic_stringbuf::pos_type.md)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[traits\_type](../Topic/basic_stringbuf::traits_type.md)|Verknüpft einen Typnamen mit dem `Tr`\-Vorlagenparameter.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Überlauf](../Topic/basic_stringbuf::overflow.md)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|  
|[pbackfail](../Topic/basic_stringbuf::pbackfail.md)|Die geschützte virtuelle Memberfunktion versucht, ein Element zurück in den Eingabepuffer zu versetzen und es dann zum aktuellen Element zu ernennen \(wird mit dem nächsten Zeiger darauf gezeigt\).|  
|[seekoff](../Topic/basic_stringbuf::seekoff.md)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[seekpos](../Topic/basic_stringbuf::seekpos.md)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[str](../Topic/basic_stringbuf::str.md)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|  
|swap||  
|[underflow](../Topic/basic_stringbuf::underflow.md)|Die geschützte virtuelle Memberfunktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.|  
  
## Anforderungen  
 **Header:** \<sstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)