---
title: codecvt-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: de7a520dea8510d3e865b4faecd50eb60d2d47a2
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689853"
---
# <a name="codecvt-class"></a>codecvt-Klasse

Eine Klassen Vorlage, die ein Objekt beschreibt, das als Gebiets Schema Aspekt fungieren kann. Sie ist in der Lage, Konvertierungen zwischen einer Sequenz von Werten zu steuern, mit denen Zeichen innerhalb des Programms codiert werden, und einer Sequenz von Werten, mit denen Zeichen außerhalb des Programms codiert werden.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>Parameter

*CharType* -\
Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.

*Byte* -\
Ein Typ, mit dem Zeichen außerhalb eines Programms codiert werden.

@No__t_1 von " *Status Type* "
Ein Typ, der verwendet werden kann, um Zwischenzustände einer Konvertierung zwischen internen und externen Zeichendarstellungen darzustellen.

## <a name="remarks"></a>Hinweise

Die Klassen Vorlage beschreibt ein Objekt, das als Gebiets Schema [Aspekt](../standard-library/locale-class.md#facet_class)fungieren kann, um Konvertierungen zwischen einer Sequenz von Werten vom Typ *CharType* und einer Sequenz von Werten vom Typ *Byte*zu steuern. Der *Statetype* -Klasse kennzeichnet die Transformation, und ein Objekt der Klasse *Statetype* speichert alle erforderlichen Zustandsinformationen während einer Konvertierung.

Die interne Codierung verwendet eine Darstellung mit einer bestimmten Anzahl von Bytes pro Zeichen, normalerweise entweder Typ **char** oder Type **wchar_t**.

Wie bei jedem Gebietsschemafacet hat das statische Objekt `id` einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in `id` gespeichert.

Die Vorlagenversionen [do_in](#do_in) und [do_out](#do_out) geben immer `codecvt_base::noconv` zurück.

Die C++- Standardbibliothek definiert einige explizite Spezialisierungen:

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

konvertiert zwischen **wchar_t** -und **char** -Sequenzen.

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

konvertiert `char16_t` zwischen als UTF-16 codierte und als UTF-8 codierte **char** -Sequenzen.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

konvertiert `char32_t` Sequenzen, die als UTF-32 (UCS-4) codiert sind, und **char** -Sequenzen, die als UTF-8 codiert sind.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[codecvt](#codecvt)|Der Konstruktor für Objekte der `codecvt`-Klasse, die als Gebietsschemafacet zur Behandlung von Konvertierungen dient.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[extern_type](#extern_type)|Ein Zeichentyp, der für externe Darstellungen verwendet wird.|
|[intern_type](#intern_type)|Ein Zeichentyp, der für interne Darstellungen verwendet wird.|
|[state_type](#state_type)|Ein Zeichentyp, der verwendet wird, um Zwischenzustände bei Konvertierungen zwischen externen und internen Darstellungen darzustellen.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[always_noconv](#always_noconv)|Testet, ob keine Konvertierungen ausgeführt werden müssen.|
|[do_always_noconv](#do_always_noconv)|Eine virtuelle Funktion, die aufgerufen wird, um zu testen, ob keine Konvertierungen ausgeführt werden müssen.|
|[do_encoding](#do_encoding)|Eine virtuelle Funktion, die testet, ob die Codierung des `Byte`-Streams zustandsabhängig ist, ob das zwischen den verwendeten `Byte`s und den `CharType`-Objekten erstellte Verhältnis konstant ist, und die im positiven Fall den Wert dieses Verhältnisses bestimmt.|
|[do_in](#do_in)|Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz interner `Byte`s in eine Sequenz externer `CharType`s zu konvertieren.|
|[do_length](#do_length)|Eine virtuelle Funktion, die bestimmt, wie viele `Byte`s aus einer angegebenen Sequenz externer `Byte`s nicht mehr als eine angegebene Anzahl von `CharType`-Objekten ergibt, und die die Anzahl von `Byte`s zurückgibt.|
|[do_max_length](#do_max_length)|Eine virtuelle Funktion, die die maximale Anzahl externer Bytes zurückgibt, die erforderlich sind, um ein internes `CharType`-Objekt zu erzeugen.|
|[do_out](#do_out)|Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz interner `CharType`-Objekte in eine Sequenz externer Bytes zu konvertieren.|
|[do_unshift](#do_unshift)|Eine virtuelle Funktion, die aufgerufen wird, um die `Byte`s bereitzustellen, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen in einer Sequenz von `Byte`s abzuschließen.|
|[encoding](#encoding)|Testet, ob die Codierung des `Byte`-Streams zustandsabhängig ist, ob das zwischen den verwendeten `Byte`s und den `CharType`-Objekten erstellte Verhältnis konstant ist, und bestimmt im positiven Fall den Wert dieses Verhältnisses.|
|[in](#in)|Konvertiert eine externe Darstellung einer Sequenz von `Byte`s in eine Darstellung einer Sequenz von `CharType`-Objekten.|
|[length](#length)|Bestimmt, wie viele `Byte`s aus einer angegebenen Sequenz externer `Byte`s nicht mehr als eine angegebene Anzahl von `CharType`-Objekten ergibt, und gibt die Anzahl von `Byte`s zurück.|
|[max_length](#max_length)|Gibt die maximale Anzahl von externen `Byte`s zurück, die erforderlich ist, um einen internen `CharType` zu erstellen.|
|[out](#out)|Konvertiert eine Sequenz interner `CharType`-Objekte in eine Sequenz externer `Byte`s.|
|[unshift](#unshift)|Stellt die externen `Byte`s bereit, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen der Sequenz von `Byte`s abzuschließen.|

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="always_noconv"></a> codecvt::always_noconv

Testet, ob keine Konvertierungen ausgeführt werden müssen.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein boolescher Wert, der **TRUE** ist, wenn keine Konvertierungen ausgeführt werden müssen; bei **FALSE** muss mindestens eine Konvertierung ausgeführt werden.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [do_always_noconv](#do_always_noconv) zurück.

### <a name="example"></a>Beispiel

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvt"></a> codecvt::codecvt

Der Konstruktor für Objekte der Klasse „codecvt“, die als Gebietsschemafacet zur Handhabung von Konvertierungen dient.

```cpp
explicit codecvt(size_t _Refs = 0);
```

### <a name="parameters"></a>Parameter

*_Refs* \
Integerwert, der zum Angeben des Speicherverwaltungstyps für das Objekt verwendet wird.

### <a name="remarks"></a>Hinweise

Die möglichen Werte für den Parameter *_Refs* und ihre Bedeutung lauten:

- 0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.

- 1: Die Lebensdauer des Objekts muss manuell verwaltet werden.

- 2: diese Werte sind nicht definiert.

Der Konstruktor initialisiert das `locale::facet` Basisobjekt mit **locale::** [Face(](../standard-library/locale-class.md#facet_class)`_Refs`).

## <a name="do_always_noconv"></a> codecvt::do_always_noconv

Eine virtuelle Funktion, die aufgerufen wird, um zu testen, ob keine Konvertierungen ausgeführt werden müssen.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die geschützte virtuelle Member-Funktion gibt nur **dann true** zurück, wenn jeder [do_in](#do_in) -oder [Do_out](#do_out) -Rückruf `noconv` zurückgibt.

Die Vorlagenversion gibt immer **TRUE** zurück.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [always_noconv](#always_noconv), das `do_always_noconv` aufruft.

## <a name="do_encoding"></a> codecvt::do_encoding

Eine virtuelle Funktion, die testet, ob die Codierung des `Byte` Streams Zustands abhängig ist, ob das Verhältnis zwischen dem verwendeten `Byte`s und dem erzeugten `CharType`s konstant ist und, wenn dies der Fall ist, den Wert dieses Verhältnisses bestimmt.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die geschützte virtuelle Memberfunktion gibt Folgendes zurück:

- -1, wenn die Codierung von Sequenzen vom Typ `extern_type` Zustands abhängig ist.

- 0, wenn die Codierung Sequenzen von variabler Länge umfasst.

- *N*, wenn die Codierung nur Sequenzen der Länge *N* umfasst.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [encoding](#encoding), mit dem `do_encoding` aufgerufen wird.

## <a name="do_in"></a> codecvt::do_in

Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz externer `Byte`s in eine Sequenz interner `CharType`s zu konvertieren.

```cpp
virtual result do_in(
    StateType& _State,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parameter

*_State* \
Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.

*First1* \
Zeiger auf den Anfang der zu konvertierenden Sequenz.

*Last1* \
Zeiger auf das Ende der zu konvertierenden Sequenz.

*next1* \
Zeiger hinter das Ende der konvertierten Sequenz auf das erste nicht konvertierte Zeichen.

*First2* \
Zeiger auf den Anfang der konvertierten Sequenz.

*Last2* \
Zeiger auf das Ende der konvertierten Sequenz.

*Next2* \
Ein Zeiger auf den `CharType`, der nach dem letzten konvertierten `CharType` steht, auf das erste unveränderte Zeichen in der Zielsequenz.

### <a name="return-value"></a>Rückgabewert

Ein Rückgabewert, der den Erfolg, den teilweisen Erfolg oder das Fehlschlagen des Vorgangs angibt. Die Funktion gibt Folgendes zurück:

- `codecvt_base::error`, wenn die Quell Sequenz nicht ordnungsgemäß formatiert ist.

- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt.

- `codecvt_base::ok`, wenn die Konvertierung erfolgreich ist.

- `codecvt_base::partial`, wenn die Quelle unzureichend ist oder das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.

### <a name="remarks"></a>Hinweise

*_State* muss den ursprünglichen Konvertierungs Zustand am Anfang einer neuen Quell Sequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. Andernfalls ist der gespeicherte Wert unspezifiziert.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [in](#in), mit dem `do_in` aufgerufen wird.

## <a name="do_length"></a> codecvt::do_length

Eine virtuelle Funktion, die bestimmt, wie viele `Byte`s aus einer angegebenen Sequenz externer `Byte`s nicht mehr als eine angegebene Anzahl von `CharType`-Objekten ergibt, und die die Anzahl von `Byte`s zurückgibt.

```cpp
virtual int do_length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>Parameter

*_State* \
Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.

*First1* \
Zeiger auf den Anfang der externen Sequenz.

*Last1* \
Zeiger auf das Ende der externen Sequenz.

*_Len2* \
Die maximale Anzahl von `Byte`s, die von der Member-Funktion zurückgegeben werden können.

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, die die maximale Anzahl von Konvertierungen darstellt, nicht größer als *_Len2*, die durch die externe Quell Sequenz bei [`first1` `last1`) definiert wird.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Member-Funktion ruft effektiv `do_in` (`_State`, `first1`, `last1`, `next1`, `_Buf`, `_Buf`  +  `_Len2`, `next2`) für *_State* (eine Kopie des Zustands), einen Puffer 1 -und-Zeiger 2and 3.

Anschließend wird `next2`  -  `buf` zurückgegeben. Daher zählt Sie die maximale Anzahl von Konvertierungen, nicht größer als *_Len2*, die durch die Quell Sequenz bei [`first1` `last1`) definiert wird.

Die Vorlagen Version gibt immer den geringeren Wert von *Last1*  - *First1* und *_Len2*zurück.

### <a name="example"></a>Beispiel

Sehen Sie sich das Beispiel für [length](#length)an, das `do_length` aufruft.

## <a name="do_max_length"></a> codecvt::do_max_length

Eine virtuelle Funktion, die die maximale Anzahl externer `Byte`s zurückgibt, die erforderlich ist, um eine interne `CharType` zu erzielen.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die maximale Anzahl von `Byte`s, die erforderlich sind, um eine `CharType` zu erhalten.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Member-Funktion gibt den größten zulässigen Wert zurück, der von [Do_length](#do_length)(`first1`, `last1`, 1) für beliebige gültige Werte von *First1* und *Last1*zurückgegeben werden kann.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [max_length](#max_length), das `do_max_length` aufruft.

## <a name="do_out"></a> codecvt::do_out

Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz interner `CharType`s in eine Sequenz externer `Byte`s zu konvertieren.

```cpp
virtual result do_out(
    StateType& _State,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parameter

*_State* \
Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.

*First1* \
Zeiger auf den Anfang der zu konvertierenden Sequenz.

*Last1* \
Zeiger auf das Ende der zu konvertierenden Sequenz.

*next1* \
Verweis auf einen Zeiger auf den ersten nicht konvertierten `CharType`, nachdem der letzte `CharType` konvertiert wurde.

*First2* \
Zeiger auf den Anfang der konvertierten Sequenz.

*Last2* \
Zeiger auf das Ende der konvertierten Sequenz.

*Next2* \
Verweis auf einen Zeiger auf den ersten nicht konvertierten `Byte`, nachdem der letzte `Byte` konvertiert wurde.

### <a name="return-value"></a>Rückgabewert

Die Funktion gibt Folgendes zurück:

- `codecvt_base::error`, wenn die Quell Sequenz nicht ordnungsgemäß formatiert ist.

- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt.

- `codecvt_base::ok`, wenn die Konvertierung erfolgreich ist.

- `codecvt_base::partial`, wenn die Quelle unzureichend ist, oder, wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.

### <a name="remarks"></a>Hinweise

*_State* muss den ursprünglichen Konvertierungs Zustand am Anfang einer neuen Quell Sequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. Andernfalls ist der gespeicherte Wert unspezifiziert.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [out](#out), mit dem `do_out` aufgerufen wird.

## <a name="do_unshift"></a> codecvt::do_unshift

Eine virtuelle Funktion, die aufgerufen wird, um die `Byte`s bereitzustellen, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen in einer Sequenz von `Byte`s abzuschließen.

```cpp
virtual result do_unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parameter

*_State* \
Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.

*First2* \
Zeiger auf die erste Position im Zielbereich.

*Last2* \
Zeiger auf die letzte Position im Zielbereich.

*Next2* \
Zeiger auf das erste unveränderte Element in der Zielsequenz.

### <a name="return-value"></a>Rückgabewert

Die Funktion gibt Folgendes zurück:

- `codecvt_base::error`, wenn _ *State* einen ungültigen Status darstellt.

- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt

- `codecvt_base::ok`, wenn die Konvertierung erfolgreich ist.

- `codecvt_base::partial`, wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Member-Funktion versucht, das Quell Element `CharType` (0) in eine Zielsequenz zu konvertieren, die in [`first2`, `last2`) gespeichert wird, mit Ausnahme des abschließenden Elements `Byte` (0). Er speichert immer in *Next2* einen Zeiger auf das erste unveränderte Element in der Zielsequenz.

_ *State* muss den ursprünglichen Konvertierungszustand am Anfang einer neuen Quellsequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. In der Regel bleibt beim Konvertieren des Quell Elements `CharType` (0) der aktuelle Zustand im ursprünglichen Konvertierungs Status.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [unshift](#unshift), mit dem `do_unshift` aufgerufen wird.

## <a name="encoding"></a> codecvt::encoding

Testet, ob die Codierung des `Byte`-Streams zustandsabhängig ist, ob das zwischen den verwendeten `Byte`s und den `CharType`-Objekten erstellte Verhältnis konstant ist, und bestimmt im positiven Fall den Wert dieses Verhältnisses.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert positiv ist, ist dieser Wert die Konstante Anzahl von `Byte` Zeichen, die für die Erstellung des `CharType` Zeichens erforderlich sind.

Die geschützte virtuelle Memberfunktion gibt Folgendes zurück:

- -1, wenn die Codierung von Sequenzen vom Typ `extern_type` Zustands abhängig ist.

- 0, wenn die Codierung Sequenzen von variabler Länge umfasst.

- *N*, wenn die Codierung nur Sequenzen der Länge *N* umfasst.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [do_encoding](#do_encoding) zurück.

### <a name="example"></a>Beispiel

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
}
```

```Output
1
1
1
```

## <a name="extern_type"></a> codecvt::extern_type

Ein Zeichentyp, der für externe Darstellungen verwendet wird.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `Byte` dar.

## <a name="in"></a> codecvt::in

Konvertiert eine externe Darstellung einer Sequenz von `Byte`s in eine Darstellung einer Sequenz von `CharType`-Objekten.

```cpp
result in(
    StateType& _State,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parameter

*_State* \
Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.

*First1* \
Zeiger auf den Anfang der zu konvertierenden Sequenz.

*Last1* \
Zeiger auf das Ende der zu konvertierenden Sequenz.

*next1* \
Zeiger hinter das Ende der konvertierten Sequenz auf das erste nicht konvertierte Zeichen.

*First2* \
Zeiger auf den Anfang der konvertierten Sequenz.

*Last2* \
Zeiger auf das Ende der konvertierten Sequenz.

*Next2* \
Ein Zeiger auf den `CharType`, der nach dem letzten konvertierten `Chartype` auf das erste unveränderte Zeichen in der Zielsequenz folgt.

### <a name="return-value"></a>Rückgabewert

Ein Rückgabewert, der den Erfolg, den teilweisen Erfolg oder das Fehlschlagen des Vorgangs angibt. Die Funktion gibt Folgendes zurück:

- `codecvt_base::error`, wenn die Quell Sequenz nicht ordnungsgemäß formatiert ist.

- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt.

- `codecvt_base::ok`, wenn die Konvertierung erfolgreich ist.

- `codecvt_base::partial`, wenn die Quelle unzureichend ist, oder, wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.

### <a name="remarks"></a>Hinweise

*_State* muss den ursprünglichen Konvertierungs Zustand am Anfang einer neuen Quell Sequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. Nach einer partiellen Konvertierung muss *_State* so festgelegt werden, dass die Konvertierung beim Eintreffen neuer Zeichen fortgesetzt werden kann.

Die Memberfunktion gibt [do_in](#do_in)( `_State`, _ *First1,  last1,  next1, First2, _Llast2,  next2*) zurück.

### <a name="example"></a>Beispiel

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="intern_type"></a> codecvt::intern_type

Ein Zeichentyp, der für interne Darstellungen verwendet wird.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `CharType` dar.

## <a name="length"></a> codecvt::length

Bestimmt, wie viele `Byte`s aus einer angegebenen Sequenz externer `Byte`s nicht mehr als eine angegebene Anzahl von `CharType`-Objekten ergibt, und gibt die Anzahl von `Byte`s zurück.

```cpp
int length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>Parameter

*_State* \
Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.

*First1* \
Zeiger auf den Anfang der externen Sequenz.

*Last1* \
Zeiger auf das Ende der externen Sequenz.

*_Len2* \
Die maximale Anzahl von Bytes, die von der Memberfunktion zurückgegeben werden kann.

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, die die maximale Anzahl von Konvertierungen darstellt, nicht größer als *_Len2*, die durch die externe Quell Sequenz bei [`first1` `last1`) definiert wird.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [do_length](#do_length)( *_State,  first1*, `last1`, `_Len2`) zurück.

### <a name="example"></a>Beispiel

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << endl;
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="max_length"></a> codecvt::max_length

Gibt die maximale Anzahl von externen `Byte`s zurück, die erforderlich ist, um einen internen `CharType` zu erstellen.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die maximale Anzahl von `Byte`s, die erforderlich sind, um eine `CharType` zu erhalten.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [do_max_length](#do_max_length) zurück.

### <a name="example"></a>Beispiel

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t> >
     ( loc ).max_length( );
   wcout << res << endl;
}
```

```Output
1
```

## <a name="out"></a> codecvt::out

Konvertiert eine Sequenz interner `CharType`-Objekte in eine Sequenz externer `Byte`s.

```cpp
result out(
    StateType& _State,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parameter

*_State* \
Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.

*First1* \
Zeiger auf den Anfang der zu konvertierenden Sequenz.

*Last1* \
Zeiger auf das Ende der zu konvertierenden Sequenz.

*next1* \
Verweis auf einen Zeiger auf den ersten nicht konvertierten `CharType` nach dem letzten konvertierten `CharType`.

*First2* \
Zeiger auf den Anfang der konvertierten Sequenz.

*Last2* \
Zeiger auf das Ende der konvertierten Sequenz.

*Next2* \
Verweis auf einen Zeiger auf den ersten nicht konvertierten `Byte` nach dem letzten konvertierten `Byte`.

### <a name="return-value"></a>Rückgabewert

Die Memberfunktion gibt [do_out](#do_out)( `_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`) zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [codecvt::do_out](#do_out).

### <a name="example"></a>Beispiel

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
   char pszExt[LEN+1];
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );
   char* pszNext;
   const wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).out( state,
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );
   pszExt[wcslen( pwszInt )] = 0;
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )
   << "The converted string is:\n ["
   << &pszExt[0]
   << "]" << endl;
}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="state_type"></a> codecvt::state_type

Ein Zeichentyp, der verwendet wird, um Zwischenzustände bei Konvertierungen zwischen externen und internen Darstellungen darzustellen.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `StateType` dar.

## <a name="unshift"></a> codecvt::unshift

Stellt die `Byte`s bereit, die in einer Zustands abhängigen Konvertierung erforderlich sind, um das letzte Zeichen in einer Sequenz von `Byte`s abzuschließen.

```cpp
result unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parameter

*_State* \
Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.

*First2* \
Zeiger auf die erste Position im Zielbereich.

*Last2* \
Zeiger auf die letzte Position im Zielbereich.

*Next2* \
Zeiger auf das erste unveränderte Element in der Zielsequenz.

### <a name="return-value"></a>Rückgabewert

Die Funktion gibt Folgendes zurück:

- `codecvt_base::error`, wenn der Zustand einen ungültigen Status darstellt.

- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt.

- `codecvt_base::ok`, wenn die Konvertierung erfolgreich ist.

- `codecvt_base::partial`, wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Member-Funktion versucht, das Quell Element `CharType` (0) in eine Zielsequenz zu konvertieren, die in [`first2`, `last2`) gespeichert wird, mit Ausnahme des abschließenden Elements `Byte` (0). Er speichert immer in *Next2* einen Zeiger auf das erste unveränderte Element in der Zielsequenz.

*_State* muss den ursprünglichen Konvertierungs Zustand am Anfang einer neuen Quell Sequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. In der Regel bleibt beim Konvertieren des Quell Elements `CharType` (0) der aktuelle Zustand im ursprünglichen Konvertierungs Status.

Die Memberfunktion gibt [do_unshift](#do_unshift)( `_State`, `first2`, `last2`, `next2` ) zurück.

## <a name="see-also"></a>Siehe auch

[\<locale>](../standard-library/locale.md)\
[Codepages](../c-runtime-library/code-pages.md)\
[Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
