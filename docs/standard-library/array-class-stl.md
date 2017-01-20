---
title: "array-Klasse (STL)"
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
  - "array/std::tr1::array"
  - "std.tr1.array"
  - "array"
  - "std::tr1::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array-Klasse [TR1]"
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
caps.latest.revision: 22
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# array-Klasse (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das eine Sequenz der Länge `N` aus Elementen des Typs `Ty` steuert.  Die Sequenz ist als ein Array von `Ty` gespeichert, das im `array<Ty, N>`\-Objekt enthalten ist.  
  
## Syntax  
  
```  
template<class Ty, std::size_t N>  
    class array;  
```  
  
#### Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Ty`|Der Typ eines Elements.|  
|`N`|Die Anzahl der Elemente.|  
  
## Mitglieder  
  
|||  
|-|-|  
|Typdefinition|Beschreibung|  
|[array::const\_iterator](../Topic/array::const_iterator.md)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[array::const\_pointer](../Topic/array::const_pointer.md)|Der Typ eines konstanten Zeigers auf ein Element.|  
|[array::const\_reference](../Topic/array::const_reference.md)|Der Typ eines konstanten Verweises auf ein Element.|  
|[array::const\_reverse\_iterator](../Topic/array::const_reverse_iterator.md)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[array::difference\_type](../Topic/array::difference_type.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[array::iterator](../Topic/array::iterator.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[array::pointer](../Topic/array::pointer.md)|Der Typ eines Zeigers auf ein Element.|  
|[array::reference](../Topic/array::reference.md)|Der Typ eines Verweises auf ein Element.|  
|[array::reverse\_iterator](../Topic/array::reverse_iterator.md)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[array::size\_type](../Topic/array::size_type.md)|Der Typ eines Abstands ohne Vorzeichen zwischen zwei Elementen.|  
|[array::value\_type](../Topic/array::value_type.md)|Der Typ eines Elements.|  
  
|||  
|-|-|  
|Memberfunktion|Beschreibung|  
|[array::array](../Topic/array::array.md)|Erstellt ein Arrayobjekt.|  
|[array::assign](../Topic/array::assign.md)|Ersetzt alle Elemente.|  
|[array::at](../Topic/array::at.md)|Greift auf ein Element an einer angegebenen Position zu.|  
|[array::back](../Topic/array::back.md)|Greift auf das letzte Element zu.|  
|[array::begin](../Topic/array::begin.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[array::cbegin](../Topic/array::cbegin.md)|Gibt einen für wahlfreien Zugriff eingerichteten konstanten Iterator auf das erste Element im Vektor zurück.|  
|[array::cend](../Topic/array::cend.md)|Gibt einen für wahlfreien Zugriff eingerichteten konstanten Iterator zurück, der unmittelbar hinter das Ende des Vektors zeigt.|  
|[array::crbegin](../Topic/array::crbegin.md)|Gibt einen konstanten Iterator zum ersten Element in einem umgekehrten Array zurück.|  
|[array::crend](../Topic/array::crend.md)|Gibt einen konstanten Iterator auf das Ende eines umgekehrten Arrays zurück.|  
|[array::data](../Topic/array::data.md)|Ruft die Adresse des ersten Elements ab.|  
|[array::empty](../Topic/array::empty.md)|Testet, ob Elemente vorhanden sind.|  
|[array::end](../Topic/array::end.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[array::fill](../Topic/array::fill.md)|Ersetzt alle Elemente durch einen angegebenen Wert.|  
|[array::front](../Topic/array::front.md)|Greift auf das erste Element zu.|  
|[array::max\_size](../Topic/array::max_size.md)|Ermittelt die Anzahl von Elementen.|  
|[array::rbegin](../Topic/array::rbegin.md)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[array::rend](../Topic/array::rend.md)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[array::size](../Topic/array::size.md)|Ermittelt die Anzahl von Elementen.|  
|[array::swap](../Topic/array::swap.md)|Vertauscht den Inhalt von zwei Containern.|  
  
|||  
|-|-|  
|Operator|Beschreibung|  
|[array::operator\=](../Topic/array::operator=.md)|Ersetzt die kontrollierte Sequenz.|  
|[array::operator](../Topic/array::operator.md)|Greift auf ein Element an einer angegebenen Position zu.|  
  
## Hinweise  
 Der Typ hat einen Standardkonstruktor `array()` und einen Standardzuweisungsoperator `operator=` und erfüllt die Anforderungen für ein `aggregate`.  Daher können Objekte des Typs `array<Ty, N>` über einen Aggregatinitialisierer initialisiert werden.  Beispiel:  
  
```  
array<int, 4> ai = { 1, 2, 3 };  
```  
  
 erstellt das Objekt `ai`, das vier ganzzahlige Werte enthält, initialisiert die ersten drei Elemente mit den Werten 1, 2 und 3 und das vierte Element mit 0.  
  
## Anforderungen  
 **Header:** \<Array\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<array\>](../standard-library/array.md)