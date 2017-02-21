---
title: "move_iterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.move_iterator"
  - "move_iterator"
  - "iterator/std::move_iterator"
  - "std::move_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "move_iterator-Klasse"
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# move_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klassenvorlage `move_iterator` ist ein Wrapper für einen Iterator.  Das move\_iterator\-Objekt stellt das gleiche Verhalten bereit wie der Iterator, der es umschließt bzw. speichert, außer, dass der Dereferenzierungsoperator des gespeicherten Iterators in einen rvalue\-Verweis und somit ein Kopier\- in ein Verschiebevorgang verwandelt wird.  Weitere Informationen zu rvalues finden Sie unter [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Syntax  
  
```  
template<class Iterator>  
    class move_iterator {  
public:  
    typedef Iterator iterator_type;  
    typedef typename      
        iterator_traits<Iterator>::iterator_category  
            iterator_category;  
    typedef typename iterator_traits<Iterator>::value_type  
        value_type;  
    typedef typename iterator_traits<Iterator>::difference_type  
        difference_type;  
    typedef Iterator  
        pointer;  
    typedef value_type&&  
        reference;  
  
    move_iterator();  
    explicit move_iterator (Iterator right);  
    template<class Type>  
        move_iterator (const move_iterator<Type>& right);  
    template <class Type>   
        move_iterator& operator=(const move_iterator<Type>& right);  
  
    iterator_type base () const;  
    reference operator* () const;  
    pointer operator-> () const;  
  
    move_iterator& operator++ ();  
    move_iterator operator++ (int);  
    move_iterator& operator-- ();  
    move_iterator operator-- (int);  
  
    move_iterator& operator+= (difference_type off);  
    move_iterator operator+ (difference_type off) const;  
    move_iterator& operator-= (difference_type off);  
    move_iterator operator- (difference_type off) const;  
    reference operator[] (difference_type off) const;  
    };  
```  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das sich wie ein Iterator verhält, außer wenn es dereferenziert wird.  Sie speichert einen Random\-Access\-Iterator vom Typ `Iterator`, auf den über die Memberfunktion `base``()` zugegriffen wird.  Alle Vorgänge für ein `move_iterator` werden direkt für den gespeicherten Iterator ausgeführt, außer dass das Ergebnis von `operator*` implizit in `value_type&&` umgewandelt wird, um einen rvalue\-Verweis zu erstellen.  
  
 Ein `move_iterator` kann Vorgänge ausführen, die nicht vom umschlossenen Iterator definiert werden.  Diese Vorgänge sollten nicht verwendet werden.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[move\_iterator](../Topic/move_iterator::move_iterator.md)|Der Konstruktor für Objekte des Typs `move_iterator`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[move\_iterator::iterator\_type](../Topic/move_iterator::iterator_type.md)|Ein Synonym für den Vorlagenparameter `RandomIterator`.|  
|[move\_iterator::iterator\_category](../Topic/move_iterator::iterator_category.md)|Als Synonym für einen längeren `typename`\-Ausdruck desselben Namens identifiziert `iterator_category` die allgemeinen Fähigkeiten des Iterators.|  
|[move\_iterator::value\_type](../Topic/move_iterator::value_type.md)|Als Synonym für einen längeren `typename`\-Ausdruck desselben Namens beschreibt `value_type` den Typ der Iteratorelemente.|  
|[move\_iterator::difference\_type](../Topic/move_iterator::difference_type.md)|Als Synonym für einen längeren `typename`\-Ausdruck desselben Namens beschreibt `difference_type` den ganzzahligen Typ, der benötigt wird, um Unterschiedswerte zwischen Elementen auszudrücken.|  
|[move\_iterator::pointer](../Topic/move_iterator::pointer.md)|Ein Synonym für den Vorlagenparameter `RandomIterator`.|  
|[move\_iterator::reference](../Topic/move_iterator::reference.md)|Ein Synonym für den `rvalue`\-Verweis `value_type&&`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[move\_iterator::base](../Topic/move_iterator::base.md)|Die Memberfunktion gibt den gespeicherten Iterator zurück, der von diesem `move_iterator` umschlossen wird.|  
  
### Operators  
  
|||  
|-|-|  
|[move\_iterator::operator\*](../Topic/move_iterator::operator*.md)|Gibt `(reference)*``base``().` zurück.|  
|[move\_iterator::operator\+\+](../Topic/move_iterator::operator++.md)|Erhöht den gespeicherten Iterator.  Das genaue Verhalten hängt davon ab, ob es sich um einen Präinkrement\- oder einen Postinkrementvorgang handelt.|  
|[move\_iterator::operator\-\-](../Topic/move_iterator::operator--.md)|Verringert den gespeicherten Iterator.  Das genaue Verhalten hängt davon ab, ob es sich um einen Prädekrement\- oder einen Postdekrementvorgang handelt.|  
|[move\_iterator::operator\-\>](../Topic/move_iterator::operator-%3E.md)|Gibt `&**this` zurück.|  
|[move\_iterator::operator\-](../Topic/move_iterator::operator-.md)|Gibt `move_iterator(*this) -=`  zurück, indem der Wert auf der rechten Seite zuerst von der aktuellen Position subtrahiert wird.|  
|[move\_iterator::operator](../Topic/move_iterator::operator.md)|Gibt `(reference)*(*this + off)` zurück.  Ermöglicht es Ihnen, ein Offset von der aktuellen Basisklasse anzugeben, um den Wert an diesem Speicherort abzurufen.|  
|[move\_iterator::operator\+](../Topic/move_iterator::operator+.md)|Gibt den Wert `move_iterator(*this) +=`  zurück.  Ermöglicht es Ihnen, ein Offset zur Basisklasse hinzuzufügen, um den Wert an diesem Speicherort abzurufen.|  
|[move\_iterator::operator\+\=](../Topic/move_iterator::operator+=.md)|Fügt dem Wert auf der rechten Seite dem gespeicherten Iterator hinzu und gibt `*this` zurück.|  
|[move\_iterator::operator\-\=](../Topic/move_iterator::operator-=.md)|Subtrahiert den Wert auf der rechten Seite vom gespeicherten Iterator und gibt `*this` zurück.|  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<iterator\>](../standard-library/iterator.md)   
 [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)   
 [Bewegungskonstruktoren und Bewegungszuweisungsoperatoren \(C\+\+\)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)   
 [Standard Template Library](../misc/standard-template-library.md)