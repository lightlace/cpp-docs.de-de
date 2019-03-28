---
title: move_iterator-Klasse
ms.date: 03/27/2019
f1_keywords:
- iterator/std::move_iterator
- iterator/std::move_iterator::iterator_type
- iterator/std::move_iterator::iterator_category
- iterator/std::move_iterator::value_type
- iterator/std::move_iterator::difference_type
- iterator/std::move_iterator::pointer
- iterator/std::move_iterator::reference
- iterator/std::move_iterator::base
helpviewer_keywords:
- std::move_iterator [C++]
- std::move_iterator [C++], iterator_type
- std::move_iterator [C++], iterator_category
- std::move_iterator [C++], value_type
- std::move_iterator [C++], difference_type
- std::move_iterator [C++], pointer
- std::move_iterator [C++], reference
- std::move_iterator [C++], base
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
ms.openlocfilehash: 3e2e62946325c082e761b6997ae584419175f8fe
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565044"
---
# <a name="moveiterator-class"></a>move_iterator-Klasse

Die Klassenvorlage `move_iterator` ist ein Wrapper für einen Iterator. Das move_iterator-Objekt stellt das gleiche Verhalten bereit wie der Iterator, der es umschließt bzw. speichert, außer, dass der Dereferenzierungsoperator des gespeicherten Iterators in einen rvalue-Verweis und somit ein Kopier- in ein Verschiebevorgang verwandelt wird. Weitere Informationen zu „rvalues“ finden Sie unter [Rvalue Reference Declarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md) (Rvalue-Verweisdeklarator: &&).

## <a name="syntax"></a>Syntax

```cpp
class move_iterator;
```

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt, das sich wie ein Iterator verhält, außer wenn es dereferenziert wird. Sie speichert einen Random-Access-Iterator des Typs `Iterator`, auf den über die Memberfunktion `base()` zugegriffen wird. Alle Vorgänge für ein `move_iterator` werden direkt für den gespeicherten Iterator ausgeführt, außer dass das Ergebnis von `operator*` implizit in `value_type&&` umgewandelt wird, um einen rvalue-Verweis zu erstellen.

Ein `move_iterator` kann Vorgänge ausführen, die nicht vom umschlossenen Iterator definiert werden. Diese Vorgänge sollten nicht verwendet werden.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[move_iterator](#move_iterator)|Der Konstruktor für Objekte des Typs `move_iterator`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[iterator_type](#iterator_type)|Ein Synonym für den Vorlagenparameter `RandomIterator`.|
|[iterator_category](#iterator_category)|Ein Synonym für einen längeren **Typename** Ausdruck mit dem gleichen Namen, `iterator_category` die allgemeinen Fähigkeiten des Iterators identifiziert.|
|[value_type](#value_type)|Ein Synonym für einen längeren **Typename** Ausdruck mit dem gleichen Namen, `value_type` wird beschrieben, was den Typ der iteratorelemente Elemente sind.|
|[difference_type](#difference_type)|Ein Synonym für einen längeren **Typename** Ausdruck mit dem gleichen Namen, `difference_type` beschreibt den ganzzahligen Typ erforderlich, um schnelle unterschiedswerte zwischen Elementen.|
|[Zeiger](#pointer)|Ein Synonym für den Vorlagenparameter `RandomIterator`.|
|[Verweis](#reference)|Ein Synonym für den `rvalue`-Verweis `value_type&&`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[base](#base)|Die Memberfunktion gibt den gespeicherten Iterator zurück, der von diesem `move_iterator` umschlossen wird.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[move_iterator::operator*](#op_star)|Gibt `(reference)*base().` zurück.|
|[move_iterator::operator++](#op_add_add)|Erhöht den gespeicherten Iterator. Das genaue Verhalten hängt davon ab, ob es sich um einen Präinkrement- oder einen Postinkrementvorgang handelt.|
|[move_iterator::operator--](#operator--)|Verringert den gespeicherten Iterator. Das genaue Verhalten hängt davon ab, ob es sich um einen Prädekrement- oder einen Postdekrementvorgang handelt.|
|[move_iterator::operator-&gt;](#op_arrow)|Gibt `&**this`zurück.|
|[move_iterator::operator-](#operator-)|Gibt `move_iterator(*this) -=` zurück, indem der Wert auf der rechten Seite zuerst von der aktuellen Position subtrahiert wird.|
|[move_iterator::operator[]](#op_at)|Gibt `(reference)*(*this + off)`zurück. Ermöglicht es Ihnen, ein Offset von der aktuellen Basisklasse anzugeben, um den Wert an diesem Speicherort abzurufen.|
|[move_iterator::operator+](#op_add)|Gibt `move_iterator(*this) +=` den Wert zurück. Ermöglicht es Ihnen, ein Offset zur Basisklasse hinzuzufügen, um den Wert an diesem Speicherort abzurufen.|
|[move_iterator::operator+=](#op_add_eq)|Fügt dem Wert auf der rechten Seite dem gespeicherten Iterator hinzu und gibt `*this` zurück.|
|[move_iterator::operator-=](#operator-_eq)|Subtrahiert den Wert auf der rechten Seite vom gespeicherten Iterator und gibt `*this` zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="base"></a> move_iterator::base

Gibt den gespeicherten Iterator für diesen `move_iterator` zurück.

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt den gespeicherten Iterator zurück.

## <a name="difference_type"></a> move_iterator::difference_type

Der Typ `difference_type` ist ein `move_iterator` `typedef` basierend auf dem Iteratormerkmal `difference_type` und kann austauschbar mit ihm verwendet werden.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>Hinweise

Der Type ist ein Synonym für das Iteratormerkmal `typename iterator_traits<RandomIterator>::pointer`.

## <a name="iterator_category"></a> move_iterator::iterator_category

Der Typ `iterator_category` ist ein `move_iterator` `typedef` basierend auf dem Iteratormerkmal `iterator_category` und kann austauschbar mit ihm verwendet werden.

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>Hinweise

Der Type ist ein Synonym für das Iteratormerkmal `typename iterator_traits<RandomIterator>::iterator_category`.

## <a name="iterator_type"></a> move_iterator::iterator_type

Der Typ `iterator_type` basiert auf dem Vorlagenparameter `RandomIterator` für die Klassenvorlage `move_iterator` und ist mit diesem wechselseitig austauschbar.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `RandomIterator` dar.

## <a name="move_iterator"></a> move_iterator::move_iterator

Erstellt einen Verschiebeiterator. Verwendet den Parameter als den gespeicherten Iterator.

```cpp
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Iterator, der als gespeicherter Iterator verwendet werden soll.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert den gespeicherten Iterator mit seinem Standardkonstruktor. Die übrigen Konstruktoren initialisieren mit den gespeicherten Iterator mit `base.base()`.

## <a name="op_add_eq"></a> move_iterator::operator+=

Fügt dem gespeicherten Iterator einen Offset hinzu, sodass der gespeicherte Iterator auf das Element an der neuen aktuellen Position zeigt. Anschließend verschiebt der Operator das neue aktuelle Element.

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parameter

*_Off*<br/>
Ein Offset, der zur aktuellen Position hinzugefügt wird, um die neue Position zu bestimmen.

### <a name="return-value"></a>Rückgabewert

Gibt das neue aktuelle Element zurück.

### <a name="remarks"></a>Hinweise

Der Operator fügt *_Off* zum gespeicherten Iterator. Danach gibt er `*this` zurück.

## <a name="operator-_eq"></a> move_iterator::operator-=

Wechselt über eine angegebene Anzahl von vorherigen Elementen. Dieser Operator subtrahiert einen Offset vom gespeicherten Iterator.

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parameter

### <a name="remarks"></a>Hinweise

Der Operator wertet `*this += -_Off` aus. Danach gibt er `*this` zurück.

## <a name="op_add_add"></a> move_iterator::operator++

Erhöht den gespeicherten Iterator zu diesem `move_iterator.` Auf das aktuelle Element wird durch den postincrement-Operator zugegriffen. Auf das nächste Element wird durch den preincrement-Operator zugegriffen.

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>Parameter

### <a name="remarks"></a>Hinweise

Der erste (preincrement-) Operator erhöht den gespeicherten Iterator. Danach gibt er `*this` zurück.

Der zweite (postincrement-)Operator erstellt eine Kopie von `*this` und wertet `++*this` aus. Anschließend gibt er die Kopie zurück.

## <a name="op_add"></a> move_iterator::operator+

Gibt die Iteratorposition an, die um eine beliebigen Anzahl von Elementen vorgerückt ist.

```cpp
move_iterator operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parameter

### <a name="remarks"></a>Hinweise

Der Operator gibt `move_iterator(*this) +=` `_Off` zurück.

## <a name="op_at"></a> move_iterator::operator[]

Erlaubt dem Arrayindex Zugriff auf Elemente im gesamten Bereich des `move iterator`.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parameter

### <a name="remarks"></a>Hinweise

Der Operator gibt `(reference)*(*this + _Off)` zurück.

## <a name="operator--"></a> move_iterator::operator--

Prä- und Postdekrement-Memberoperatoren führen ein Dekrement für den gespeicherten Iterator aus.

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>Parameter

### <a name="remarks"></a>Hinweise

Der erste Memberoperator (Prädekrement) dekrementiert den gespeicherten Iterator. Danach gibt er `*this` zurück.

Der zweite Operator (Postdekrement, Dekrement in Postfix-Notation) erstellt eine Kopie von `*this` und berechnet dann `--*this`. Anschließend gibt er die Kopie zurück.

## <a name="operator-"></a> move_iterator::operator-

Dekrementiert den gespeicherten Iterator und gibt den gekennzeichneten Wert zurück.

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>Parameter

### <a name="remarks"></a>Hinweise

Der Operator gibt `move_iterator(*this) -= _Off` zurück.

## <a name="op_star"></a> move_iterator::operator*

Dereferenziert den gespeicherten Iterator und gibt den Wert zurück. Dies verhält sich wie eine `rvalue reference` und führt eine Verschiebezuordnung aus. Der Operator überträgt das aktuelle Element aus dem Basisiterator heraus. Das darauf folgende Element wird das neue aktuelle Element.

```cpp
reference operator*() const;
```

### <a name="remarks"></a>Hinweise

Der Operator gibt `(reference)*base()` zurück.

## <a name="op_arrow"></a> move_iterator::operator-&gt;

Wie ein normaler `RandomIterator``operator->` bietet dieser Operator Zugriff auf die Felder, die zum aktuellen Element gehören.

```cpp
pointer operator->() const;
```

### <a name="remarks"></a>Hinweise

Der Operator gibt `&**this` zurück.

## <a name="pointer"></a> move_iterator::pointer

Der Typ `pointer` ist eine **Typedef** basierend auf dem zufallsiterator `RandomIterator` für `move_iterator`, und können austauschbar verwendet werden.

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `RandomIterator`.

## <a name="reference"></a> move_iterator::reference

Der Typ `reference` ist eine **Typedef** basierend auf `value_type&&` für `move_iterator`, und kann austauschbar mit `value_type&&`.

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `value_type&&`, der ein Rvalue-Verweis ist.

## <a name="value_type"></a> move_iterator::value_type

Der Typ `value_type` ist ein `move_iterator` `typedef` basierend auf dem Iteratormerkmal `value_type` und kann austauschbar mit ihm verwendet werden.

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>Hinweise

Der Type ist ein Synonym für das Iteratormerkmal `typename iterator_traits<RandomIterator>::value_type`.

## <a name="see-also"></a>Siehe auch

[\<iterator>](../standard-library/iterator.md)<br/>
[Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
[Bewegungskonstruktoren und Bewegungszuweisungsoperatoren (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
