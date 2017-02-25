---
title: "basic_string-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_string"
  - "std::basic_string"
  - "basic_string"
  - "xstring/std::basic_string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_string-Klasse"
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# basic_string-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei den von einem Objekt der `basic_string`\-Vorlagenklasse gesteuerten Sequenzen handelt es sich um die Standard\-C\+\+\-Zeichenfolgenklasse, und sie werden normalerweise als Zeichenfolgen bezeichnet. Allerdings sollten diese nicht mit den in der C\+\+\-Standardbibliothek verwendeten auf NULL endenden Zeichenfolgen im C\-Stil verwechselt werden.  Die C\+\+\-Standardzeichenfolge ist ein Container, der die Verwendung von Zeichenfolgen als Normaltypen, wie das Verwenden von Vergleichs\- und Verkettungsvorgängen, Iteratoren, STL\-Algorithmen sowie das Kopieren und Zuweisen mit von Klassenzuweisung verwaltetem Arbeitsspeicher, ermöglicht.  Falls eine C\+\+\-Standardzeichenfolge in eine auf Null endende Zeichenfolge im C\-Stil konvertiert werden muss, verwenden Sie den [basic\_string::c\_str](../Topic/basic_string::c_str.md)\-Member.  
  
## Syntax  
  
```  
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>> class basic_string;  
```  
  
#### Parameter  
 `CharType`  
 Der Datentyp eines einzelnen in der Zeichenfolge zu speichernden Zeichens.  Die C\+\+\-Standardbibliothek bietet Spezialisierungen dieser Vorlagenklasse mit den Typdefinitionen [string](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md) für Elemente des Typs `char`, [wstring](../Topic/wstring.md) für `wchar_t`, [u16string](../Topic/u16string.md) für `char16_t` und [u32string](../Topic/u32string.md) für `char32_t`.  
  
 `Traits`  
 Verschiedene wichtige Eigenschaften der **CharType**\-Elemente in einer basic\_string\-Spezialisierung werden von der Klasse **Traits** beschrieben.  Der Standardwert ist `char_traits`\<`CharType`\>.  
  
 `Allocator`  
 Der Typ, mit dem das gespeicherte Zuordnungsobjekt darstellt wird, mit dem Details zum Belegen und Freigeben des Arbeitsspeichers der Zeichenfolge gekapselt werden.  Der Standardwert ist **allocator**\<`CharType`\>.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_string](../Topic/basic_string::basic_string.md)|Erstellt eine Zeichenfolge, die leer ist, oder von bestimmten Zeichen initialisiert wird, oder eine vollständige oder teilweise Kopie eines anderen Zeichenfolgenobjekts oder einer C\-Zeichenfolge ist.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_string::allocator_type.md)|Ein Typ, mit dem die `allocator`\-Klasse für ein Zeichenfolgenobjekt dargestellt wird.|  
|[const\_iterator](../Topic/basic_string::const_iterator.md)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem auf ein `const`\-Element zugegriffen, und mit dem dieses Element gelesen werden kann.|  
|[const\_pointer](../Topic/basic_string::const_pointer.md)|Ein Typ, der einen Zeiger auf ein `const`\-Element in einer Zeichenfolge bereitstellt.|  
|[const\_reference](../Topic/basic_string::const_reference.md)|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einer Zeichenfolge zum Lesen und Ausführen von `const`\-Vorgängen gespeichert ist.|  
|[const\_reverse\_iterator](../Topic/basic_string::const_reverse_iterator.md)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes `const`\-Element gelesen werden kann.|  
|[difference\_type](../Topic/basic_string::difference_type.md)|Ein Typ, der den Unterschied zwischen zwei Iteratoren, die auf Elemente innerhalb derselben Zeichenfolge verweisen, bereitstellt.|  
|[Iterator](../Topic/basic_string::iterator.md)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einer Zeichenfolge gelesen oder geändert werden kann.|  
|[npos](../Topic/basic_string::npos.md)|Ein auf – 1 initialisierter Integralwert ohne Vorzeichen, der bei einem Fehler mit einer Suchfunktion entweder "nicht gefunden" oder "alle verbleibenden Zeichen" angibt.|  
|[pointer](../Topic/basic_string::pointer.md)|Ein Typ, der einen Zeiger auf ein Zeichenelement in einer Zeichenfolge oder einem Zeichenarray bereitstellt.|  
|[Verweis](../Topic/basic_string::reference.md)|Ein Typ, der einen Verweis auf ein in einer Zeichenfolge gespeichertes Element bereitstellt.|  
|[reverse\_iterator](../Topic/basic_string::reverse_iterator.md)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem ein Element in einer umgekehrten Zeichenfolge gelesen oder geändert werden kann.|  
|[size\_type](../Topic/basic_string::size_type.md)|Ein Integraltyp ohne Vorzeichen für die Anzahl von Elementen in einer Zeichenfolge.|  
|[traits\_type](../Topic/basic_string::traits_type.md)|Ein Typ für die Zeichenmerkmale der in einer Zeichenfolge gespeicherten Elemente.|  
|[value\_type](../Topic/basic_string::value_type.md)|Ein Typ, der die Art der in einer Zeichenfolge gespeicherten Zeichen darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[append](../Topic/basic_string::append.md)|Fügt am Ende einer Zeichenfolge Zeichen hinzu.|  
|[assign](../Topic/basic_string::assign.md)|Weist dem Inhalt einer Zeichenfolge neue Zeichenwerte zu.|  
|[at](../Topic/basic_string::at.md)|Gibt einen Verweis auf das Element an einer angegebenen Position in der Zeichenfolge zurück.|  
|[back](../Topic/basic_string::back.md)||  
|[begin](../Topic/basic_string::begin.md)|Gibt ein Iterator zurück, der das erste Element in der Zeichenfolge adressiert.|  
|[c\_str](../Topic/basic_string::c_str.md)|Konvertiert den Inhalt einer Zeichenfolge als eine auf NULL endende Zeichenfolge im C\-Format zurück.|  
|[Kapazität](../Topic/basic_string::capacity.md)|Gibt die höchste Anzahl von Elementen zurück, die ohne Erhöhung der Speicherbelegung der Zeichenfolge in einer Zeichenfolge gespeichert werden können.|  
|[cbegin](../Topic/basic_string::cbegin.md)|Gibt einen const\-Iterator zurück, der das erste Element in der Zeichenfolge adressiert.|  
|[cend](../Topic/basic_string::cend.md)|Gibt einen const\-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Zeichenfolge nachfolgt.|  
|[clear](../Topic/basic_string::clear.md)|Löscht alle Elemente einer Zeichenfolge.|  
|[compare](../Topic/basic_string::compare.md)|Vergleicht eine Zeichenfolge mit einer angegebenen Zeichenfolge, um zu bestimmen, ob die beiden Zeichenfolgen gleich sind, oder ob eine lexikografisch kleiner als die andere ist.|  
|[copy](../Topic/basic_string::copy.md)|Kopiert höchstens eine angegebene Anzahl von Zeichen aus einer indizierten Position in einer Quellzeichenfolge in ein Zielzeichenarray.  Veraltet.  Verwenden Sie stattdessen [basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md).|  
|[crbegin](../Topic/basic_string::crbegin.md)|Gibt einen const\-Iterator zurück, der das erste Element in einer umgekehrter Zeichenfolge adressiert.|  
|[crend](../Topic/basic_string::crend.md)|Gibt einen const\-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Zeichenfolge nachfolgt.|  
|[\_Copy\_s](../Topic/basic_string::_Copy_s.md)|Kopiert höchstens eine angegebene Anzahl von Zeichen aus einer indizierten Position in einer Quellzeichenfolge in ein Zielzeichenarray.|  
|[Daten](../Topic/basic_string::data.md)|Konvertiert den Inhalt einer Zeichenfolge in ein Zeichenarray.|  
|[empty](../Topic/basic_string::empty.md)|Testet, ob in der Zeichenfolge Zeichen enthalten sind.|  
|[end](../Topic/basic_string::end.md)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Zeichenfolge nachfolgt.|  
|[Löschen](../Topic/basic_string::erase.md)|Entfernt ein Element oder einen Reihe von Elementen einer Zeichenfolge von einer angegebenen Position.|  
|[find](../Topic/basic_string::find.md)|Sucht eine Zeichenfolge vorwärts nach dem ersten Vorkommen einer Teilzeichenfolge ab, die mit einer bestimmten Zeichensequenz übereinstimmt.|  
|[find\_first\_not\_of](../Topic/basic_string::find_first_not_of.md)|Durchsucht eine Zeichenfolge nach dem ersten Zeichen, das kein Element der angegebenen Zeichenfolge ist.|  
|[find\_first\_of](../Topic/basic_string::find_first_of.md)|Durchsucht eine Zeichenfolge nach dem ersten Zeichen, das einem Element der angegebenen Zeichenfolge entspricht.|  
|[find\_last\_not\_of](../Topic/basic_string::find_last_not_of.md)|Durchsucht eine Zeichenfolge nach dem letzten Zeichen, das kein Element der angegebenen Zeichenfolge ist.|  
|[find\_last\_of](../Topic/basic_string::find_last_of.md)|Durchsucht eine Zeichenfolge nach dem letzten Zeichen, das ein Element der angegebenen Zeichenfolge ist.|  
|[front](../Topic/basic_string::front.md)|Gibt einen Verweis auf das erste Element in einer Zeichenfolge zurück.|  
|[get\_allocator](../Topic/basic_string::get_allocator.md)|Gibt eine Kopie des zum Erstellen der Zeichenfolge verwendeten `allocator`\-Objekts zurück.|  
|[Einfügen](../Topic/basic_string::insert.md)|Fügt ein Element oder mehrere Elemente oder ein Reihe von Elementen an einer bestimmten Position in die Zeichenfolge ein.|  
|[length](../Topic/basic_string::length.md)|Gibt die aktuelle Anzahl von Elementen in einer Zeichenfolge zurück.|  
|[max\_size](../Topic/basic_string::max_size.md)|Gibt die Höchstanzahl von Zeichen, die eine Zeichenfolge enthalten könnte zurück.|  
|[pop\_back](../Topic/basic_string::pop_back.md)|Löscht das letzte Element der Zeichenfolge.|  
|[push\_back](../Topic/basic_string::push_back.md)|Fügt ein Element am Ende der Zeichenfolge hinzu.|  
|[rbegin](../Topic/basic_string::rbegin.md)|Gibt einen Iterator an das erste Element in einer umgekehrten Zeichenfolge zurück.|  
|[rend](../Topic/basic_string::rend.md)|Gibt einen Iterator zurück, der auf die Position direkt hinter dem letzten Element in einer umgekehrten Zeichenfolge zeigt.|  
|[replace](../Topic/basic_string::replace.md)|Ersetzt Elemente an einer bestimmten Position in einer Zeichenfolge durch angegebene Zeichen oder Zeichen, die aus anderen Bereichen oder Zeichenfolgen oder C\-Zeichenfolgen kopiert werden.|  
|[reserve](../Topic/basic_string::reserve.md)|Legt die Kapazität der Zeichenfolge auf eine Zahl fest, die mindestens so groß ist, wie eine angegebene Anzahl.|  
|[resize](../Topic/basic_string::resize.md)|Gibt eine neue Größe für eine Zeichenfolge an und fügt Elemente an bzw. löscht sie bei Bedarf.|  
|[rfind](../Topic/basic_string::rfind.md)|Sucht eine Zeichenfolge rückwärts nach dem ersten Vorkommen einer Teilzeichenfolge ab, die mit einer bestimmten Zeichensequenz übereinstimmt.|  
|[shrink\_to\_fit](../Topic/basic_string::shrink_to_fit.md)|Verwirft die Überkapazität der Zeichenfolge.|  
|[size](../Topic/basic_string::size.md)|Gibt die aktuelle Anzahl von Elementen in einer Zeichenfolge zurück.|  
|[substr](../Topic/basic_string::substr.md)|Kopiert eine Teilzeichenfolge höchstens einer beliebigen Anzahl von Zeichen aus einer Zeichenfolge, beginnend an einer angegebenen Position.|  
|[swap](../Topic/basic_string::swap.md)|Tauschen Sie den Inhalt von zwei Zeichenfolgen aus.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \+\=](../Topic/basic_string::operator+=.md)|Fügt einer Zeichenfolge Zeichen an.|  
|[operator \=](../Topic/basic_string::operator=.md)|Weist dem Inhalt einer Zeichenfolge neue Zeichenwerte zu.|  
|[operator&#91;&#93;](../Topic/basic_string::operator.md)|Stellt mit einem angegebenen Index in einer Zeichenfolge einen Verweis auf das Zeichen.|  
  
## Hinweise  
 Wenn eine Funktion aufgefordert wird, eine Sequenz zu generieren, die länger als [max\_size](../Topic/basic_string::max_size.md)\-Elemente ist, wird von der Funktion ein Längenfehler gemeldet, indem ein Objekt des Typs [length\_error](../standard-library/length-error-class.md) ausgelöst wird.  
  
 Verweise, Zeiger und Iteratoren, mit denen Elemente der gesteuerte Sequenz festgelegt werden, können nach jedem Aufruf einer Funktion, mit der die gesteuerte Sequenz geändert wird, oder nach dem ersten Aufruf einer anderen als einer **const**\-Memberfunktion ungültig werden.  
  
## Anforderungen  
 **Header:** \<string\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<string\>](../standard-library/string.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)