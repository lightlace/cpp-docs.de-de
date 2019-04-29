---
title: money_put-Klasse
ms.date: 11/01/2018
f1_keywords:
- xlocmon/std::money_put
- xlocmon/std::money_put::char_type
- xlocmon/std::money_put::iter_type
- xlocmon/std::money_put::string_type
- xlocmon/std::money_put::do_put
- xlocmon/std::money_put::put
helpviewer_keywords:
- std::money_put [C++]
- std::money_put [C++], char_type
- std::money_put [C++], iter_type
- std::money_put [C++], string_type
- std::money_put [C++], do_put
- std::money_put [C++], put
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
ms.openlocfilehash: 346dd4f681432143c954ca125c3862fc6827db60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383541"
---
# <a name="moneyput-class"></a>money_put-Klasse

Die Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von monetären Werten in Sequenzen vom Typ `CharType` zu steuern.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class money_put : public locale::facet;
```

### <a name="parameters"></a>Parameter

*CharType*<br/>
Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.

*OutputIterator*<br/>
Der Typ des Iterators, in den die monetären Put-Funktionen ihre Ausgabe schreiben.

## <a name="remarks"></a>Hinweise

Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **id** gespeichert.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[money_put](#money_put)|Der Konstruktor für Objekte des Typs `money_put`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|
|[iter_type](#iter_type)|Ein Typ, der einen Ausgabeiterator beschreibt.|
|[string_type](#string_type)|Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen vom Typ `CharType` enthält.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[do_put](#do_put)|Eine virtuelle Funktion, die aufgerufen wird, um entweder eine Zahl oder eine Zeichenfolge in eine Zeichenfolge zu konvertieren, die einen monetären Wert darstellt.|
|[put](#put)|Konvertiert entweder eine Zahl oder eine Zeichenfolge in eine Zeichenfolge, die einen monetären Wert darstellt.|

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="char_type"></a> money_put::char_type

Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter **CharType** dar.

## <a name="do_put"></a> money_put::do_put

Eine virtuelle Funktion, die aufgerufen wird, um entweder eine Zahl oder eine Zeichenfolge in eine Zeichenfolge zu konvertieren, die einen monetären Wert darstellt.

```cpp
virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;

virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>Parameter

*next*<br/>
Ein Iterator, der das erste Element in der eingefügten Zeichenfolge adressiert.

*_Intl*<br/>
Ein boolescher Wert, der den Typ des in der Sequenz vorgesehenen Währungssymbols angibt (**TRUE**, wenn international; **FALSE**, wenn national).

*_Iosbase*<br/>
Ein Formatkennzeichen, das bei Verwendung angibt, dass das Währungssymbol optional ist. Ansonsten ist das Währungssymbol erforderlich.

*_Fill*<br/>
Ein Zeichen, das Leerzeichen einfügt.

*val*<br/>
Ein zu konvertierendes Zeichenfolgenobjekt.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der auf die erste Position nach dem jeweils letzten Element verweist.

### <a name="remarks"></a>Hinweise

Der erste virtuelle geschützte Memberfunktion generiert sequenzielle Elemente ab *Weiter* zum Erzeugen der Ausgabefelder für monetäre Werte aus der ["string_type"](#string_type) Objekt *Val*. Die gesteuerte Sequenz durch *Val* muss beginnen mit einem oder mehreren Dezimalstellen, optional mit vorangestelltem Minuszeichen (-), die den Betrag darstellen. Die Funktion gibt einen Iterator zurück, der das erste Element nach dem generierten Ausgabefeld für monetäre Werte festlegt.

Der zweite virtuelle geschützte Memberfunktion verhält sich genauso wie die erste, außer, dass die It effektiv zuerst *Val* konvertiert Sie in eine Folge von Dezimalziffern, optional mit vorangestelltem ein Minuszeichen (-), klicken Sie dann diese Sequenz wie oben beschrieben.

Das Format eines Eingabefelds für monetäre Werte richtet sich nach dem [Gebietsschemafacet](../standard-library/locale-class.md#facet_class) „fac“, das durch den (effektiven) Aufruf [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**> >( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)) zurückgegeben wird.

Dies gilt insbesondere in folgenden Fällen:

- **fac**. [pos_format](../standard-library/moneypunct-class.md#pos_format) bestimmt die Reihenfolge, in der Komponenten des Felds für einen nicht negativen Wert generiert werden.

- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) bestimmt die Reihenfolge, in der Komponenten des Felds für einen negativen Wert generiert werden.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) bestimmt die Sequenz von Elementen, die für ein Währungssymbol erzeugt werden soll.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) bestimmt die Sequenz von Elementen, die für ein positives Vorzeichen generiert werden soll.

- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) bestimmt die Sequenz von Elementen, die für ein negatives Vorzeichen generiert werden soll.

- **fac**. [grouping](../standard-library/moneypunct-class.md#grouping) bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.

- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) bestimmt das Element, das Gruppen von Ziffern auf der linken Seite eines Dezimaltrennzeichens trennt.

- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) bestimmt das Element, das ganzzahlige Ziffern von Bruchziffern trennt.

- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) bestimmt die Anzahl signifikanter Bruchziffern auf der rechten Seite eines Dezimaltrennzeichens.

Wenn die Zeichenfolge ( **fac**. `negative_sign` oder **fac**. `positive_sign`) über mehr als ein Element verfügt, wird nur das erste Element generiert, bei dem das dem **money_base::sign** entsprechende Element im Formatmuster ( **fac**. `neg_format` oder **fac**. `pos_format`) angezeigt wird. Alle übrigen Elemente werden am Ende des Ausgabefelds für monetäre Werte generiert.

Wenn **iosbase**. [flags](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) ungleich 0 (null) ist, wird die Zeichenfolge **fac**. `curr_symbol` dort generiert, wo das dem **money_base::symbol** entsprechende Element im Formatmuster angezeigt wird. Andernfalls wird kein Währungssymbol generiert.

Erfolgen keine Gruppierungseinschränkungen durch **fac**. **grouping** (sein erstes Element weist den Wert CHAR_MAX auf), werden keine Instanzen von **fac**. `thousands_sep` im Wertteil des Ausgabefelds für monetäre Werte generiert (in dem das dem **money_base::symbol** entsprechende Element im Formatmuster angezeigt wird). Wenn **fac**. `frac_digits` 0 (null) ist, wird keine Instanz von **fac**. `decimal_point` nach den Dezimalstellen generiert. Ansonsten platziert das jeweilige Ausgabefeld für monetäre Werte die niederwertigen **fac**. `frac_digits`-Dezimalstellen auf der rechten Seite des Dezimaltrennzeichens.

Abstände treten wie bei Ausgabefeldern für numerische Werte auf. Wenn **iosbase**. **flags** & **iosbase**. [internal](../standard-library/ios-functions.md#internal) ungleich 0 (null) ist, werden jedoch alle internen Abstände dort generiert, wo das dem **money_base::space** entsprechende Element im Formatmuster angezeigt wird (sofern es angezeigt wird). Andernfalls treten interne Abstände vor der generierten Sequenz auf. Das Füllzeichen ist **fill**.

Die Funktion ruft **iosbase**. **width**(0) auf, um die Feldbreite auf 0 (null) zurückzusetzen.

### <a name="example"></a>Beispiel

Informationen hierzu finden Sie im Beispiel für [put](#put), bei dem die virtuelle Memberfunktion durch **put** aufgerufen wird.

## <a name="iter_type"></a> money_put::iter_type

Ein Typ, der einen Ausgabeiterator beschreibt.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Vorlagenparameter **OutputIterator**.

## <a name="money_put"></a> money_put::money_put

Der Konstruktor für Objekte des Typs `money_put`.

```cpp
explicit money_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parameter

*_Refs*<br/>
Integerwert, der zum Angeben des Speicherverwaltungstyps für das Objekt verwendet wird.

### <a name="remarks"></a>Hinweise

Die möglichen Werte für die *_Refs* Parameter und ihre Bedeutung:

- 0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.

- 1: Die Lebensdauer des Objekts muss manuell verwaltet werden.

- \> 1: Diese Werte sind nicht definiert.

Direkte Beispiele hierfür sind nicht möglich, da der Destruktor geschützt ist.

Der Konstruktor initialisiert sein Basisobjekt mit **locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`).

## <a name="put"></a> money_put::put

Konvertiert entweder eine Zahl oder eine Zeichenfolge in eine Zeichenfolge, die einen monetären Wert darstellt.

```cpp
iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;

iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>Parameter

*next*<br/>
Ein Iterator, der das erste Element in der eingefügten Zeichenfolge adressiert.

*_Intl*<br/>
Ein boolescher Wert, der den Typ des in der Sequenz vorgesehenen Währungssymbols angibt (**TRUE**, wenn international; **FALSE**, wenn national).

*_Iosbase*<br/>
Ein Formatkennzeichen, das bei Verwendung angibt, dass das Währungssymbol optional ist. Ansonsten ist das Währungssymbol erforderlich.

*_Fill*<br/>
Ein Zeichen, das Leerzeichen einfügt.

*val*<br/>
Ein zu konvertierendes Zeichenfolgenobjekt.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der auf die erste Position nach dem jeweils letzten Element verweist.

### <a name="remarks"></a>Hinweise

Beide Memberfunktionen geben [do_put](#do_put)( `next`, `_Intl`, `_Iosbase`, `_Fill`, `val`) zurück.

### <a name="example"></a>Beispiel

```cpp
// money_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

int main()
{
    std::locale loc( "german_germany" );
    std::basic_stringstream<char> psz;

    psz.imbue(loc);
    psz.flags(psz.flags() | std::ios_base::showbase); // force the printing of the currency symbol
    std::use_facet<std::money_put<char> >(loc).put(std::basic_ostream<char>::_Iter(psz.rdbuf()), true, psz, ' ', 100012);
    if (psz.fail())
        std::cout << "money_put() FAILED" << std::endl;
    else
        std::cout << "money_put() = \"" << psz.rdbuf()->str() << "\"" << std::endl;
}
```

```Output
money_put() = "EUR1.000,12"
```

## <a name="string_type"></a> money_put::string_type

Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen vom Typ `CharType` enthält.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [basic_string](../standard-library/basic-string-class.md), deren Objekte Elementsequenzen aus der Quellsequenz speichern können.

## <a name="see-also"></a>Siehe auch

[\<locale>](../standard-library/locale.md)<br/>
[Facet-Klasse](../standard-library/locale-class.md#facet_class)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
