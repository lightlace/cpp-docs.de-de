---
title: "&lt;type_traits&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<type_traits>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typetrait-Header [TR1]"
  - "type_traits"
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
caps.latest.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# &lt;type_traits&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Vorlagen, die während der Kompilierung\-Konstanten, die Informationen zu den Eigenschaften ihrer Typargumente geben oder erzeugen Typen transformiert bereitstellen.  
  
## Syntax  
  
```  
#include <type_traits>  
```  
  
## Hinweise  
 Die Klassen und Vorlagen in `<type_traits>` dienen zur Unterstützung des Typrückschlusses, Klassifizierung und die Transformation zum Zeitpunkt der Kompilierung, um Fehler im Zusammenhang mit Typ zu erkennen, und können Sie generischen Code optimieren. Diese Klassen und Vorlagen umfassen unäre Typeigenschaften, die eine Eigenschaft eines Typs beschreiben Binärtyp Merkmale, die beschreiben eine Beziehung zwischen Typen und Transformation Merkmale, die eine Eigenschaft eines Typs zu ändern.  
  
 Zur Unterstützung von Typeigenschaften, eine Hilfsklasse `integral_constant`, definiert ist. Es hat vorlagenspezialisierungen `true_type` und `false_type` die die Basisklassen für Typ Prädikate bilden. Ein *typprädikat* ist eine Vorlage, die eine oder mehrere Typargumente entgegennimmt. Wenn ein Typprädikat *true* ist, wird es öffentlich, direkt oder indirekt aus [true\_type](../Topic/true_type%20Typedef.md) abgeleitet. Wenn ein Typprädikat *false* ist, wird es öffentlich, direkt oder indirekt aus [false\_type](../Topic/false_type%20Typedef.md) abgeleitet.  
  
 Ein *Typmodifizierer* oder *Transformation Merkmal* ist eine Vorlage, die eine oder mehrere Vorlagenargumente entgegennimmt und verfügt über einen Member `type`, dies ist ein Synonym für den geänderten Typ.  
  
### Alias\-Vorlagen  
 Zur Vereinfachung der Typ "traits"\-Ausdrücke, [aliasvorlagen](../cpp/aliases-and-typedefs-cpp.md) für `typename some_trait<T>::type` zur Verfügung, wobei " `some_trait`" ist der Klassenname für die Vorlage. Beispielsweise [Add\_const](../standard-library/add-const-class.md) verfügt über einen Alias\-Vorlage für seinen Typ `add_const_t`, definiert als:  
  
```cpp  
template<class T>  
    using add_const_t = typename add_const<T>::type;  
```  
  
|||||  
|-|-|-|-|  
|add\_const\_t|aligned\_storage\_t|make\_signed\_t|remove\_pointer\_t|  
|add\_cv\_t|aligned\_union\_t|make\_unsigned\_t|remove\_reference\_t|  
|add\_lvalue\_reference\_t|common\_type\_t|remove\_all\_extents\_t|remove\_volatile\_t|  
|add\_pointer\_t|conditional\_t|remove\_const\_t|result\_of\_t|  
|add\_rvalue\_reference\_t|decay\_t|remove\_cv\_t|underlying\_type\_t|  
|add\_volatile\_t|enable\_if\_t|remove\_extent\_t||  
  
### Klassen  
 Hilfsklasse und Typdefinitionen  
  
|||  
|-|-|  
|[integral\_constant](../standard-library/integral-constant-class-bool-constant-class.md)|Macht einen ganzzahligen Konstanten aus einem Typ und einem Wert.|  
|[true\_type](../Topic/true_type%20Typedef.md)|Enthält eine Ganzzahlkonstante mit einem wahren Wert.|  
|[false\_type](../Topic/false_type%20Typedef.md)|Enthält eine Ganzzahlkonstante mit einem falschen Wert.|  
  
 Primäre Kategorien  
  
|||  
|-|-|  
|[is\_void](../standard-library/is-void-class.md)|Testet, ob der Typ ist `void`.|  
|[is\_null\_pointer](../standard-library/is-null-pointer-class.md)|Testet, ob der Typ ist `std::nullptr_t`.|  
|[is\_integral](../standard-library/is-integral-class.md)|Testet, ob der Typ eine Ganzzahl ist.|  
|[is\_floating\_point](../standard-library/is-floating-point-class.md)|Testet, ob der Typ ein Gleitkomma ist.|  
|[is\_array](../standard-library/is-array-class.md)|Testet, ob der Typ ein Array ist.|  
|[is\_pointer](../standard-library/is-pointer-class.md)|Testet, ob der Typ ein Zeiger ist.|  
|[is\_lvalue\_reference](../standard-library/is-lvalue-reference-class.md)|Testet, ob es sich beim Typ um einen lvalue\-Verweis handelt.|  
|[is\_rvalue\_reference](../standard-library/is-rvalue-reference-class.md)|Testet, ob es sich beim Typ um einen „rvalue“\-Verweis handelt.|  
|[is\_member\_object\_pointer](../standard-library/is-member-object-pointer-class.md)|Testet, ob der Typ ein Zeiger auf ein Memberobjekt ist.|  
|[is\_member\_function\_pointer](../standard-library/is-member-function-pointer-class.md)|Testet, ob der Typ ein Zeiger auf eine Memberfunktion ist.|  
|[is\_enum](../standard-library/is-enum-class.md)|Testet, ob der Typ eine Aufzählung ist.|  
|[is\_union](../standard-library/is-union-class.md)|Testet, ob der Typ eine Union ist.|  
|[is\_class](../standard-library/is-class-class.md)|Testet, ob der Typ eine Klasse ist.|  
|[is\_function](../standard-library/is-function-class.md)|Testet, ob der Typ ein Funktionstyp ist.|  
  
 Zusammengesetzter Typ Kategorien  
  
|||  
|-|-|  
|[is\_reference](../standard-library/is-reference-class.md)|Testet, ob der Typ ein Verweis ist.|  
|[is\_arithmetic](../standard-library/is-arithmetic-class.md)|Testet, ob der Typ arithmetisch ist.|  
|[is\_fundamental](../standard-library/is-fundamental-class.md)|Testet, ob der Typ `void` oder arithmetisch ist.|  
|[is\_object](../standard-library/is-object-class.md)|Testet, ob der Typ ein Objekttyp ist.|  
|[is\_scalar](../standard-library/is-scalar-class.md)|Testet, ob der Typ skalar ist.|  
|[is\_compound](../standard-library/is-compound-class.md)|Testet, ob der Typ nicht skalar ist.|  
|[is\_member\_pointer](../standard-library/is-member-pointer-class.md)|Testet, ob der Typ ein Zeiger auf ein Member ist.|  
  
 Eigenschaften des Typs  
  
|||  
|-|-|  
|[is\_const](../standard-library/is-const-class.md)|Testet, ob der Typ ist `const`.|  
|[is\_volatile](../standard-library/is-volatile-class.md)|Testet, ob der Typ ist `volatile`.|  
|[is\_trivial](../standard-library/is-trivial-class.md)|Testet, ob der Typ trivial ist.|  
|[is\_trivially\_copyable](../standard-library/is-trivially-copyable-class.md)|Testet, ob der Typ belanglos kopierbar ist.|  
|[is\_standard\_layout](../standard-library/is-standard-layout-class.md)|Testet, ob der Typ ein Standardlayout ist.|  
|[is\_pod](../standard-library/is-pod-class.md)|Testet, ob der Typ ein POD\-Typ ist.|  
|[is\_literal\_type](../standard-library/is-literal-type-class.md)|Testet, ob der Typ werden kann ein `constexpr` Variable oder verwendet eine `constexpr` Funktion.|  
|[is\_empty](../standard-library/is-empty-class.md)|Testet, ob es sich bei dem Typ um eine leere Klasse handelt.|  
|[is\_polymorphic](../standard-library/is-polymorphic-class.md)|Testet, ob der Typ eine polymorphe Klasse ist.|  
|[is\_abstract](../standard-library/is-abstract-class.md)|Testet, ob es dich bei dem Typ um eine abstrakte Klasse handelt.|  
|[is\_final](../standard-library/is-final-class.md)|Testet, ob der Typ ein Klassentyp gekennzeichnet ist `final`.|  
|[is\_signed](../standard-library/is-signed-class.md)|Testet, ob der Typ eine Ganzzahl mit einem Vorzeichen ist.|  
|[is\_unsigned](../standard-library/is-unsigned-class.md)|Testet, ob der Typ eine Ganzzahl ohne Vorzeichen ist.|  
|[is\_constructible](../standard-library/is-constructible-class.md)|Testet, ob der Typ mit den angegebenen Argumenttypen erstellbaren ist.|  
|[is\_default\_constructible](../standard-library/is-default-constructible-class.md)|Testet, ob der Typ einen Standardkonstruktor verfügt.|  
|[is\_copy\_constructible](../standard-library/is-copy-constructible-class.md)|Testet, ob der Typ einen Kopierkonstruktor verfügt.|  
|[is\_move\_constructible](../standard-library/is-move-constructible-class.md)|Testet, ob der Typ einen Verschiebungskonstruktor aufweist.|  
|[is\_assignable](../standard-library/is-assignable-class.md)|Testet, ob der erste Typ einen Wert des zweiten Typs zugewiesen werden kann.|  
|[is\_copy\_assignable](../standard-library/is-copy-assignable-class.md)|Testet, ob ein Typ einen Konstanten Verweiswert des Typs zugewiesen werden kann.|  
|[is\_move\_assignable](../standard-library/is-move-assignable-class.md)|Testet, ob ein Typ einen Rvalue\-Verweis des Typs zugewiesen werden kann.|  
|[is\_destructible](../standard-library/is-destructible-class.md)|Testet, ob der Typ „destructible“ ist.|  
|[is\_trivially\_constructible](../standard-library/is-trivially-constructible-class.md)|Testet, ob der Typ keine nicht trivialen Vorgänge beim Verwenden der angegebenen Typen verwendet.|  
|[is\_trivially\_default\_constructible](../standard-library/is-trivially-default-constructible-class.md)|Testet, ob der Typ keine nicht trivialen Vorgänge verwendet, wenn der Standardwert erstellt.|  
|[is\_trivially\_copy\_constructible](../standard-library/is-trivially-copy-constructible-class.md)|Testet, ob der Typ keine nicht trivialen Vorgänge verwendet, wenn Kopie erstellt.|  
|[is\_trivially\_move\_constructible](../standard-library/is-trivially-move-constructible-class.md)|Testet, ob der Typ keine nicht trivialen Vorgänge verwendet, wenn verschieben erstellt.|  
|[is\_trivially\_assignable](../standard-library/is-trivially-assignable-class.md)|Testet, ob die Typen zugeordnet werden können und die keine nicht trivialen Vorgänge verwendet.|  
|[is\_trivially\_copy\_assignable](../standard-library/is-trivially-copy-assignable-class.md)|Testet, ob der Typ kopieren zugewiesen werden kann und die Zuweisung ist keine nicht trivialen Vorgänge verwendet.|  
|[is\_trivially\_move\_assignable](../standard-library/is-trivially-move-assignable-class.md)|Testet, ob der Typ verschieben zugeordnet werden kann und die Zuweisung ist keine nicht trivialen Vorgänge verwendet.|  
|[is\_trivially\_destructible](../standard-library/is-trivially-destructible-class.md)|Überprüft, ob der Typ zerstörbaren und der Destruktor keine nicht trivialen Vorgänge verwendet.|  
|[is\_nothrow\_constructible](../standard-library/is-nothrow-constructible-class.md)|Überprüft, ob der Typ erstellt und bekannt ist, auslösen, wenn mithilfe des angegebenen Typs erstellt.|  
|[is\_nothrow\_default\_constructible](../standard-library/is-nothrow-default-constructible-class.md)|Tests, ob der Typ standardmäßig erstellt und ist bekannt nicht auslösen, wenn der Standardwert erstellt.|  
|[is\_nothrow\_copy\_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|Überprüft, ob der Typ Kopie erstellt und der Kopierkonstruktor bekannt ist, auslösen.|  
|[is\_nothrow\_move\_constructible](../standard-library/is-nothrow-move-constructible-class.md)|Testet, ob der Typ erstellbaren verschieben und der verschiebekonstruktor bekannt ist aus.|  
|[is\_nothrow\_assignable](../standard-library/is-nothrow-assignable-class.md)|Testet, ob der Typ mit dem angegebenen Typ zugeordnet ist, und die Zuweisung aus bekannt ist.|  
|[is\_nothrow\_copy\_assignable](../standard-library/is-nothrow-copy-assignable-class.md)|Testet, ob der Kopie zugeordnet ist und die Zuweisung aus bekannt ist.|  
|[is\_nothrow\_move\_assignable](../standard-library/is-nothrow-move-assignable-class.md)|Überprüft, ob der Typ verschieben zugeordnet werden kann und die Zuweisung bekannt ist, auslösen.|  
|[is\_nothrow\_destructible](../standard-library/is-nothrow-destructible-class.md)|Testet, ob der Typ zerstörbaren ist und der Destruktor aus bekannt ist.|  
|[has\_virtual\_destructor](assetId:///c0f85f0b-c63c-410d-a046-72eeaf44f7eb)|Testet, ob der Typ einen virtuellen Destruktor aufweist.|  
  
 Eigenschaftsabfragen  
  
|||  
|-|-|  
|[alignment\_of](../standard-library/alignment-of-class.md)|Ruft die Ausrichtung eines Typs ab.|  
|[rank](../standard-library/rank-class.md)|Ruft die Anzahl von Arraydimensionen ab.|  
|[extent](../standard-library/extent-class.md)|Ruft die Anzahl der Elemente in die Dimension des angegebenen Arrays ab.|  
  
 Datentyp  
  
|||  
|-|-|  
|[is\_same](../standard-library/is-same-class.md)|Stellt fest, ob zwei Typen identisch sind.|  
|[is\_base\_of](../standard-library/is-base-of-class.md)|Testet, ob ein Typ eine Basis eines anderen ist.|  
|[is\_convertible](../standard-library/is-convertible-class.md)|Testet, ob ein Typ in einen anderen konvertiert werden kann.|  
  
 Const\-Volatile\-Änderungen  
  
|||  
|-|-|  
|[add\_const](../standard-library/add-const-class.md)|Erzeugt eine `const` Art von Typ.|  
|[add\_volatile](../standard-library/add-volatile-class.md)|Erzeugt eine `volatile` Art von Typ.|  
|[add\_cv](../standard-library/add-cv-class.md)|Erzeugt eine `const``volatile` Typ vom Typ.|  
|[remove\_const](../standard-library/remove-const-class.md)|Erzeugt einen non\-Const\-Typ vom Typ.|  
|[remove\_volatile](../standard-library/remove-volatile-class.md)|Erzeugt einen permanenten Typ Typs.|  
|[remove\_cv](../standard-library/remove-cv-class.md)|Erzeugt einen nicht flüchtigen Typ nicht Const\-Typs.|  
  
 Referenz\-Änderungen  
  
|||  
|-|-|  
|[add\_lvalue\_reference](../standard-library/add-lvalue-reference-class.md)|Erstellt einen Verweis auf die aus dem Typ.|  
|[add\_rvalue\_reference](../standard-library/add-rvalue-reference-class.md)|Erzeugt einen Rvalue\-Verweis aus dem Typ|  
|[remove\_reference](../standard-library/remove-reference-class.md)|Erstellt einen non\-Reference Typ vom Typ.|  
  
 Anmeldung ändern  
  
|||  
|-|-|  
|[make\_signed](../standard-library/make-signed-class.md)|Der Typ, wenn signiert oder den kleinsten Typ mit Vorzeichen größer als oder gleich groß Eingabe ergibt.|  
|[make\_unsigned](../standard-library/make-unsigned-class.md)|Der Typ, wenn nicht signierte oder den kleinsten Typ ohne Vorzeichen größer als oder gleich groß Eingabe ergibt.|  
  
 Array\-Änderungen  
  
|||  
|-|-|  
|[remove\_all\_extents](../standard-library/remove-all-extents-class.md)|Erstellt einen Arraytyp aus einem Arraytyp.|  
|[remove\_extent](../standard-library/remove-extent-class.md)|Der Typ des Elements aus einem Arraytyp wird erzeugt.|  
  
 Zeiger\-Änderungen  
  
|||  
|-|-|  
|[add\_pointer](../standard-library/add-pointer-class.md)|Erzeugt einen Zeiger auf die aus dem Typ.|  
|[remove\_pointer](../standard-library/remove-pointer-class.md)|Erzeugt einen Typ von einem Zeiger auf den Typ an.|  
  
 Andere Transformationen  
  
|||  
|-|-|  
|[aligned\_storage](../standard-library/aligned-storage-class.md)|Weist nicht initialisierten Arbeitsspeicher für eine ausgerichteten Typ zu.|  
|[aligned\_union](../standard-library/aligned-union-class.md)|Weist den nicht initialisierten Arbeitsspeicher für eine ausgerichtete Union mit einem nicht trivialen Konstruktor oder Destruktor zu.|  
|[common\_type](../standard-library/common-type-class.md)|Der allgemeine Typ aller Typen des parameterpakets erzeugt.|  
|[conditional](../standard-library/conditional-class.md)|Wenn die Bedingung true ist, erzeugt der ersten angegebenen Typ andernfalls den zweiten Typ.|  
|[decay](../standard-library/decay-class.md)|Der Typ wird erzeugt, als Wert übergeben. Erstellt einen non\-reference\-, non\-const\- oder non\-volatile\-Typ oder erstellt einen Zeiger auf den Typ.|  
|[enable\_if](../standard-library/enable-if-class.md)|Wenn die Bedingung true ist, erzeugt dem angegebenen Typ andernfalls keinen Typ.|  
|[result\_of](../standard-library/result-of-class1.md)|Bestimmt den Rückgabetyp des Typs aufgerufen werden kann, die die angegebenen Argumenttypen akzeptiert.|  
|[underlying\_type](../standard-library/underlying-type-class.md)|Erstellt den zugrunde liegenden ganzzahligen Typ für einen Enumerationstyp.|  
  
## Siehe auch  
 [\<functional\>](../standard-library/functional.md)