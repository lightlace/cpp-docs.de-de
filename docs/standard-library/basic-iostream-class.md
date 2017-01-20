---
title: "basic_iostream-Klasse"
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
  - "istream/std::basic_iostream"
  - "std.basic_iostream"
  - "basic_iostream"
  - "std::basic_iostream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_iostream-Klasse"
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# basic_iostream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Streamklasse für Ein\- und Ausgabe.  
  
## Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_iostream : public basic_istream<Elem, Tr>,  
        public basic_ostream<Elem, Tr>  
{  
public:  
    explicit basic_iostream(basic_streambuf<Elem, Tr> *_Strbuf);  
    virtual ~basic_iostream();  
};  
```  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das Einfügevorgänge über seine Basisklasse [basic\_ostream](../standard-library/basic-ostream-class.md)\<`Elem``Tr`\> und Extraktionen über seine Basisklasse [basic\_istream](../standard-library/basic-istream-class.md)\<`Elem``Tr`\> steuert.  Die beiden Objekte nutzen gemeinsam die virtuelle Basisklasse [basic\_ios](../standard-library/basic-ios-class.md)\<`Elem``Tr`\>.  Außerdem verwalten sie einen gemeinsamen Streampuffer mit Elementen des Typs `Elem`, deren Zeichenmerkmale durch die `Tr`\-Klasse bestimmt sind.  Der Konstruktor initialisiert seine Basisklassen über `basic_istream`\(**strbuf**\) und `basic_ostream`\(**strbuf**\).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_iostream](../Topic/basic_iostream::basic_iostream.md)|Erstellen eines `basic_iostream`\-Objekts|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[swap](../Topic/basic_iostream::swap.md)|Tauscht den Inhalt des bereitgestellten `basic_iostream`\-Objekts mit dem Inhalt dieses Objekts aus.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_iostream::operator=.md)|Weist diesem Objekt den Wert eines angegebenen `basic_iostream`\-Objekts zu .  Dies ist eine Verschiebezuweisung über einen `rvalue`, die keine Kopie hinterlässt.|  
  
## Anforderungen  
 **Header:** \<istream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)