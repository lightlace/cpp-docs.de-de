---
title: ios_base-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xiosbase/std::ios_base
- ios/std::ios_base::event_callback
- xiosbase/std::ios_base::fmtflags
- xiosbase/std::ios_base::iostate
- xiosbase/std::ios_base::openmode
- xiosbase/std::ios_base::seekdir
- xiosbase/std::ios_base::event
- xiosbase/std::ios_base::adjustfield
- xiosbase/std::ios_base::app
- xiosbase/std::ios_base::ate
- xiosbase/std::ios_base::badbit
- xiosbase/std::ios_base::basefield
- xiosbase/std::ios_base::beg
- xiosbase/std::ios_base::binary
- xiosbase/std::ios_base::boolalpha
- xiosbase/std::ios_base::cur
- xiosbase/std::ios_base::dec
- xiosbase/std::ios_base::end
- xiosbase/std::ios_base::eofbit
- xiosbase/std::ios_base::failbit
- xiosbase/std::ios_base::fixed
- xiosbase/std::ios_base::floatfield
- xiosbase/std::ios_base::goodbit
- xiosbase/std::ios_base::hex
- xiosbase/std::ios_base::in
- xiosbase/std::ios_base::internal
- xiosbase/std::ios_base::left
- xiosbase/std::ios_base::oct
- xiosbase/std::ios_base::out
- xiosbase/std::ios_base::right
- xiosbase/std::ios_base::scientific
- xiosbase/std::ios_base::showbase
- xiosbase/std::ios_base::showpoint
- xiosbase/std::ios_base::showpos
- xiosbase/std::ios_base::skipws
- xiosbase/std::ios_base::trunc
- xiosbase/std::ios_base::unitbuf
- xiosbase/std::ios_base::uppercase
- xiosbase/std::ios_base::failure
- xiosbase/std::ios_base::flags
- xiosbase/std::ios_base::getloc
- xiosbase/std::ios_base::imbue
- xiosbase/std::ios_base::Init
- xiosbase/std::ios_base::iword
- xiosbase/std::ios_base::precision
- xiosbase/std::ios_base::pword
- ios/std::ios_base::register_callback
- xiosbase/std::ios_base::setf
- xiosbase/std::ios_base::sync_with_stdio
- xiosbase/std::ios_base::unsetf
- xiosbase/std::ios_base::width
- xiosbase/std::ios_base::xalloc
dev_langs:
- C++
helpviewer_keywords:
- std::ios_base [C++]
- std::ios_base [C++], event_callback
- std::ios_base [C++], fmtflags
- std::ios_base [C++], iostate
- std::ios_base [C++], openmode
- std::ios_base [C++], seekdir
- std::ios_base [C++], event
- std::ios_base [C++], adjustfield
- std::ios_base [C++], app
- std::ios_base [C++], ate
- std::ios_base [C++], badbit
- std::ios_base [C++], basefield
- std::ios_base [C++], beg
- std::ios_base [C++], binary
- std::ios_base [C++], boolalpha
- std::ios_base [C++], cur
- std::ios_base [C++], dec
- std::ios_base [C++], end
- std::ios_base [C++], eofbit
- std::ios_base [C++], failbit
- std::ios_base [C++], fixed
- std::ios_base [C++], floatfield
- std::ios_base [C++], goodbit
- std::ios_base [C++], hex
- std::ios_base [C++], in
- std::ios_base [C++], internal
- std::ios_base [C++], left
- std::ios_base [C++], oct
- std::ios_base [C++], out
- std::ios_base [C++], right
- std::ios_base [C++], scientific
- std::ios_base [C++], showbase
- std::ios_base [C++], showpoint
- std::ios_base [C++], showpos
- std::ios_base [C++], skipws
- std::ios_base [C++], trunc
- std::ios_base [C++], unitbuf
- std::ios_base [C++], uppercase
- std::ios_base [C++], failure
- std::ios_base [C++], flags
- std::ios_base [C++], getloc
- std::ios_base [C++], imbue
- std::ios_base [C++], Init
- std::ios_base [C++], iword
- std::ios_base [C++], precision
- std::ios_base [C++], pword
- std::ios_base [C++], register_callback
- std::ios_base [C++], setf
- std::ios_base [C++], sync_with_stdio
- std::ios_base [C++], unsetf
- std::ios_base [C++], width
- std::ios_base [C++], xalloc
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adf94e8443b6001c7ee142b734eedb3969eec02a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="iosbase-class"></a>ios_base-Klasse

Die Klasse beschreibt die Speicher- und Memberfunktionen, die Eingabe- und Ausgabestreams gemeinsam sind, die nicht von den Vorlagenparametern abhängen. (Die Vorlagenklasse [basic_ios](../standard-library/basic-ios-class.md) beschreibt, welche Funktionen gemeinsam und von Vorlagenparametern abhängig sind.)

Ein Objekt der ios_base-Klasse speichert Formatierungsinformationen, die aus Folgendem bestehen:

- Formatflags in einem Objekt vom Typ [fmtflags](#fmtflags).

- Eine Ausnahmemaske in einem Objekt vom Typ [iostate](#iostate).

- Eine Feldbreite in ein Objekt des Typs `int`.

- Eine Anzeigegenauigkeit in einem Objekt vom Typ `int`.

- Ein Gebietsschemaobjekt in einem Objekt vom Typ **locale**.

- Zwei erweiterbare Arrays mit Elementen vom Typ **long** und `void`-Zeiger.

Ein Objekt der ios_base-Klasse speichert auch Streamzustandsinformationen in einem Objekt des Typs [iostate](#iostate) und einen Rückrufstapel.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[ios_base](#ios_base)|Erstellt `ios_base`-Objekte.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[event_callback](#event_callback)|Beschreibt eine Funktion, die an [register_call](#register_callback) übergeben wird.|
|[fmtflags](#fmtflags)|Konstanten, mit denen das Aussehen der Ausgabe angegeben wird.|
|[iostate](#iostate)|Definiert Konstanten, die den Zustand eines Streams beschreiben.|
|[openmode](#openmode)|Beschreibt, wie mit einem Stream interagiert wird.|
|[seekdir](#seekdir)|Gibt den Startpunkt für Offsetvorgänge an.|

### <a name="enums"></a>Enumerationen

|||
|-|-|
|[event](#event)|Gibt Ereignistypen an.|

### <a name="constants"></a>Konstanten

|||
|-|-|
|[adjustfield](#fmtflags)|Eine Bitmaske, die als `internal` &#124; `left` &#124; `right` definiert ist.|
|[app](#openmode)|Gibt an, dass vor jedem Einfügevorgang bis zum Ende eines Streams gesucht werden soll.|
|[ate](#openmode)|Gibt an, dass bis zum Ende eines Streams gesucht werden soll, wenn dessen steuerndes Objekt erstmalig erstellt wird.|
|[badbit](#iostate)|Protokolliert einen Verlust der Integrität des Streampuffers.|
|[basefield](#fmtflags)|Eine Bitmaske, die als `dec` &#124; `hex` &#124; `oct` definiert ist.|
|[beg](#seekdir)|Gibt an, dass relativ zum Anfang einer Sequenz gesucht werden soll.|
|[binary](#openmode)|Gibt an, dass eine Datei als binärer Stream und nicht als Textstream gelesen werden soll.|
|[boolalpha](#fmtflags)|Gibt an, dass Objekte vom Typ `bool` als Namen (wie `true` und `false`) statt als numerische Werte eingefügt oder extrahiert werden sollen.|
|[cur](#seekdir)|Gibt an, dass in einer Sequenz relativ zur aktuellen Position gesucht werden soll.|
|[dec](#fmtflags)|Gibt an, dass ganzzahlige Werte im Dezimalformat eingefügt oder extrahiert werden sollen.|
|[end](#seekdir)|Gibt an, dass relativ zum Ende einer Sequenz gesucht werden soll.|
|[eofbit](#iostate)|Protokolliert beim Extrahieren aus einem Stream das Dateiende.|
|[failbit](#iostate)|Protokolliert einen Fehler beim Extrahieren eines gültigen Felds aus einem Stream.|
|[fixed](#fmtflags)|Gibt an, dass Gleitkommawerte im Festkommaformat (ohne Exponentenfeld) eingefügt werden sollen.|
|[floatfield](#fmtflags)|Eine Bitmaske, die als `fixed` &#124; `scientific` definiert ist|
|[goodbit](#iostate)|Kein Zustandsbit ist gesetzt.|
|[hex](#fmtflags)|Gibt an, dass ganzzahlige Werte im Hexadezimalformat eingefügt oder extrahiert werden sollen.|
|[in](#openmode)|Gibt die Extraktion aus einem Stream an.|
|[internal](#fmtflags)|Füllt bis zu einer Feldbreite auf, indem Füllzeichen an einem Punkt eingefügt werden, der sich intern in einem generierten numerischen Feld befindet.|
|[left](#fmtflags)|Gibt linksbündige Ausrichtung an.|
|[oct](#fmtflags)|Gibt an, dass ganzzahlige Werte im Oktalformat eingefügt oder extrahiert werden sollen.|
|[out](#openmode)|Gibt die Einfügung in einen Stream an.|
|[right](#fmtflags)|Gibt rechtsbündige Ausrichtung an.|
|[scientific](#fmtflags)|Gibt an, dass Gleitkommawerte im wissenschaftlichen Format (mit Exponentenfeld) eingefügt werden sollen.|
|[showbase](#fmtflags)|Gibt die Einfügung eines Präfixes an, das die Basis eines generierten ganzzahigen Felds angibt.|
|[showpoint](#fmtflags)|Gibt die unbedingte Einfügung eines Dezimaltrennzeichens in einem generierten Gleitkommafeld an.|
|[showpos](#fmtflags)|Gibt die Einfügung eines Pluszeichens (+) in einem nicht negativen generierten numerischen Feld an.|
|[skipws](#fmtflags)|Gibt an, dass führende Leerzeichen vor bestimmten Extraktionen übersprungen werden sollen.|
|[trunc](#openmode)|Gibt an, dass der Inhalt einer vorhandenen Datei gelöscht werden soll, wenn deren steuerndes Objekt erstellt wird.|
|[unitbuf](#fmtflags)|Bewirkt, dass die Ausgabe nach jeder Einfügung geleert wird.|
|[uppercase](#fmtflags)|Gibt an, dass bei bestimmten Einfügevorgängen die Großbuchstaben eingefügt werden, die den Kleinbuchstaben entsprechen.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[failure](#failure)|Die Memberklasse dient als Basisklasse für alle Ausnahmen, die von der Memberfunktion [clear](../standard-library/basic-ios-class.md#clear) in der Vorlagenklasse [basic_ios](../standard-library/basic-ios-class.md) ausgelöst werden.|
|[flags](#flags)|Legt die aktuellen Flageinstellungen fest oder gibt sie zurück.|
|[getloc](#getloc)|Gibt das gespeicherte Gebietsschemaobjekt zurück.|
|[imbue](#imbue)|Ändert das Gebietsschema.|
|[Init](#init)|Erstellt bei der Konstruktion die iostream-Standardobjekte.|
|[iword](#iword)|Weist einen als `iword` zu speichernden Wert zu.|
|[precision](#precision)|Gibt die Anzahl der anzuzeigenden Ziffern in einer Gleitkommazahl an.|
|[pword](#pword)|Weist einen als `pword` zu speichernden Wert zu.|
|[register_callback](#register_callback)|Gibt eine Rückruffunktion an.|
|[setf](#setf)|Legt die angegebenen Flags fest.|
|[sync_with_stdio](#sync_with_stdio)|Stellt sicher, dass iostream-Vorgänge und Vorgänge der C-Laufzeitbibliothek in der Reihenfolge ausgeführt werden, in der sie im Quellcode stehen.|
|[unsetf](#unsetf)|Bewirkt, dass die angegebenen Flags deaktiviert werden.|
|[width](#width)|Legt die Länge des Ausgabestreams fest.|
|[xalloc](#xalloc)|Gibt an, dass eine Variable Teil des Streams sein soll.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Der Zuweisungsoperator für `ios_base`-Objekte.|

## <a name="requirements"></a>Anforderungen

**Header:** \<ios>

**Namespace:** std

## <a name="event"></a> ios_base::event

Gibt Ereignistypen an.

```cpp
enum event {
    erase_event,
    imbue_event,
    copyfmt_event};
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Aufzählungstyp, der ein Objekt beschreibt, das ein Rückrufereignis speichern kann, das als Argument für eine Funktion verwendet wird, die mit [register_callback](#register_callback) registriert wurde. Die unterschiedlichen Ereigniswerte lauten:

- **copyfmt_event** zur Identifizierung eines Rückrufs, der gegen Ende eines Aufrufs an [copyfmt](../standard-library/basic-ios-class.md#copyfmt) auftritt, kurz bevor die [exception mask](../standard-library/ios-base-class.md) kopiert wird.

- **erase_event** zur Identifizierung eines Rückrufs, der zu Beginn eines Aufrufs an [copyfmt](../standard-library/basic-ios-class.md#copyfmt) oder zu Beginn eines Aufrufs an den Destruktor für **\*this** auftritt.

- **imbue_event** zur Identifizierung eines Rückrufs, der gegen Ende eines Aufrufs an [imbue](#imbue) auftritt, kurz bevor die Funktion zurückspringt.

### <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter [register_callback](#register_callback).

## <a name="event_callback"></a> ios_base::event_callback

Beschreibt eine Funktion, die an [register_call](#register_callback) übergeben wird.

```cpp
typedef void (__cdecl *event_callback)(
    event _E,
    ios_base& _Base,
    int _I);
```

### <a name="parameters"></a>Parameter

*_E* der [Ereignis](#event).

`_Base` Der Stream, in dem das Ereignis aufgerufen wurde.

*_Ich* eine benutzerdefinierte Zahl.

### <a name="remarks"></a>Hinweise

Der Typ definiert einen Zeiger auf eine Funktion, die mit [register_callback](#register_callback) registriert werden kann. Der Typ der Funktion darf keine Ausnahme auslösen.

### <a name="example"></a>Beispiel

Ein Beispiel, in dem `event_callback` verwendet wird, finden Sie unter [register_call](#register_callback).

## <a name="failure"></a> ios_base::failure

Die Klasse `failure` definiert die Basisklasse für alle Typen von Objekten, die von Funktionen in der `iostreams`-Bibliothek als Ausnahmen ausgelöst wurden, um Fehler zu melden, die während der Streampuffervorgänge erkannt wurden.

```cpp
namespace std {
    class failure : public system_error {
    public:
        explicit failure(
            const string& _Message,
            const error_code& _Code = io_errc::stream);

        explicit failure(
            const char* str,
            const error_code& _Code = io_errc::stream);
    };
}
```

### <a name="remarks"></a>Hinweise

Der von `what()` zurückgegebene Wer ist eine Kopie von `_Message`, die möglicherweise mit einem auf `_Code` basierten Test erweitert wurde. Wenn kein `_Code` angegeben wird, lautet der Standardwert `make_error_code(io_errc::stream)`.

### <a name="example"></a>Beispiel

```cpp
// ios_base_failure.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.exceptions(ios::failbit);
    try
    {
        file.open( "rm.txt", ios_base::in );
        // Opens nonexistent file for reading
    }
    catch( ios_base::failure f )
    {
        cout << "Caught an exception: " << f.what() << endl;
    }
}
```

```Output
Caught an exception: ios_base::failbit set
```

## <a name="flags"></a> ios_base::flags

Legt die aktuellen Flageinstellungen fest oder gibt sie zurück.

```cpp
fmtflags flags() const;
fmtflags flags(fmtflags fmtfl);
```

### <a name="parameters"></a>Parameter

`fmtfl` Die neue `fmtflags` Einstellung.

### <a name="return-value"></a>Rückgabewert

Die vorherige oder aktuelle Einstellung `fmtflags`.

### <a name="remarks"></a>Hinweise

Eine Liste der Flags finden Sie unter [ios_base::fmtflags](#fmtflags).

Die erste Memberfunktion gibt die gespeicherten Formatflags zurück. Die zweite Memberfunktion speichert `fmtfl` in den Formatflags und gibt den zuletzt gespeicherten Wert zurück.

### <a name="example"></a>Beispiel

```cpp
// ios_base_flags.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    cout << cout.flags( ) << endl;
    cout.flags( ios::dec | ios::boolalpha );
    cout << cout.flags( );
}
```

```Output
513
16896
```

## <a name="fmtflags"></a> ios_base::fmtflags

Konstanten, mit denen das Aussehen der Ausgabe angegeben wird.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type fmtflags;
   static const fmtflags boolalpha;
   static const fmtflags dec;
   static const fmtflags fixed;
   static const fmtflags hex;
   static const fmtflags internal;
   static const fmtflags left;
   static const fmtflags oct;
   static const fmtflags right;
   static const fmtflags scientific;
   static const fmtflags showbase;
   static const fmtflags showpoint;
   static const fmtflags showpos;
   static const fmtflags skipws;
   static const fmtflags unitbuf;
   static const fmtflags uppercase;
   static const fmtflags adjustfield;
   static const fmtflags basefield;
   static const fmtflags floatfield;
   // ...
};
```

### <a name="remarks"></a>Hinweise

Unterstützt die Manipulatoren in [ios](../standard-library/ios.md).

Der Typ ist ein Bitmaskentyp, der ein Objekt beschreibt, das Formatflags speichern kann. Die unterschiedlichen Flagwerte (Elemente) sind:

- `dec`, um ganzzahlige Werte im Dezimalformat einzufügen oder zu extrahieren.

- `hex`, um ganzzahlige Werte im Hexadezimalformat einzufügen oder zu extrahieren.

- `oct`, um ganzzahlige Werte im Oktalformat einzufügen oder zu extrahieren.

- `showbase`, um ein Präfix einzufügen, das die Basis eines generierten ganzzahligen Felds angibt.

- `internal`, um nach Bedarf bis zu einer Feldbreite aufzufüllen, indem Füllzeichen an einem Punkt eingefügt werden, der sich intern in einem generierten numerischen Feld befindet. (Informationen, wie die Breite eines Felds festgelegt wird, finden Sie unter [setw](../standard-library/iomanip-functions.md#setw)).

- `left`, um nach Bedarf bis zu einer Feldbreite aufzufüllen, indem Füllzeichen am Ende eines generierten Feld angefügt werden (linksbündig ausrichten).

- `right`, um nach Bedarf bis zu einer Feldbreite aufzufüllen, indem Füllzeichen am Anfang eines generierten Feld eingefügt werden (rechtsbündig ausrichten).

- `boolalpha`, um Objekte des Typs `bool` nicht als numerische Werte, sondern als Namen (z. B. `true` und `false`) einzufügen oder zu extrahieren.

- `fixed`, um Gleitkommawerte im Festkommaformat (ohne Exponentenfeld) einzufügen.

- `scientific`, um Gleitkommawerte im wissenschaftlichen Format (mit Exponentenfeld) einzufügen.

- `showpoint`, um ein Dezimaltrennzeichen unbedingt in ein generiertes Gleitkommafeld einzufügen.

- `showpos`, um ein Pluszeichens in ein generiertes nicht negatives numerisches Feld einzufügen.

- `skipws`, um führende Leerzeichen vor bestimmten Extraktionen zu überspringen.

- `unitbuf`, um die Ausgabe nach jedem Einfügevorgang zu leeren.

- `uppercase`, um bei bestimmten Einfügevorgängen die Großbuchstaben einzufügen, die den Kleinbuchstaben entsprechen.

Zusätzlich gibt es weitere nützliche Werte:

- `adjustfield`, eine Bitmaske, die als `internal` &#124; `left` &#124; `right` definiert ist

- `basefield`, definiert als `dec` &#124; `hex` &#124; `oct`

- `floatfield`, definiert als `fixed` &#124; `scientific`

Beispiele zu Funktionen, die diese Formatflags ändern, finden Sie unter [\<iomanip>](../standard-library/iomanip.md).

## <a name="getloc"></a> ios_base::getloc

Gibt das gespeicherte Gebietsschemaobjekt zurück.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Rückgabewert

Das gespeicherte Gebietsschemaobjekt.

### <a name="example"></a>Beispiel

```cpp
// ios_base_getlock.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << cout.getloc( ).name( ).c_str( ) << endl;
}
```

```Output
C
```

## <a name="imbue"></a> ios_base::imbue

Ändert das Gebietsschema.

```cpp
locale imbue(const locale& _Loc);
```

### <a name="parameters"></a>Parameter

`_Loc` Die neue Einstellung für das Benutzergebietsschema.

### <a name="return-value"></a>Rückgabewert

Das vorherige Gebietsschema.

### <a name="remarks"></a>Hinweise

Die Member Funktion speichert `_Loc` im Gebietsschemaobjekt und meldet dann das Rückrufereignis und das `imbue_event`. Es gibt den zuletzt gespeicherten Wert zurück.

### <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue).

## <a name="init"></a> ios_base::Init

Erstellt bei der Konstruktion die iostream-Standardobjekte.

```cpp
class Init { };
```

### <a name="remarks"></a>Hinweise

Die geschachtelte Klasse beschreibt ein Objekt, dessen Konstruktion sicherstellt, dass die iostreams-Standardobjekte richtig konstruiert sind; dies geschieht sogar schon vor der Ausführung eines Konstruktors für ein willkürliches statisches Objekt.

## <a name="ios_base"></a> ios_base::ios_base

Konstruiert ios_base-Objekte.

```cpp
ios_base();
```

### <a name="remarks"></a>Hinweise

Der (geschützte) Konstruktor führt keine Aktion aus. Ein späterer Aufruf an **basic_ios::**[init](../standard-library/basic-ios-class.md#init) muss das Objekt initialisieren, bevor es sicher zerstört werden kann. Deshalb ist der einzige sichere Gebrauch für die ios_base-Klasse der Gebrauch als Basisklasse für die Vorlagenklassen [basic_ios](../standard-library/basic-ios-class.md).

## <a name="iostate"></a> ios_base::iostate

Der Typ der Konstanten, die den Zustand eines Streams beschreiben.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Bitmaskentyp, der ein Objekt beschreibt, das Informationen zum Streamzustand speichern kann. Die unterschiedlichen Flagwerte (Elemente) sind:

- `badbit` zur Protokollierung eines Verlusts der Integrität des Streampuffers.

- `eofbit` zur Protokollierung des Dateiendes beim Extrahieren aus einem Stream.

- `failbit` zur Protokollierung eines Fehlers beim Extrahieren eines gültigen Felds aus einem Stream.

Wenn keines der oben genannten Bits festgelegt ist, ist `goodbit` ein nützlicher Wert (`goodbit` ist auf jeden Fall 0).

## <a name="iword"></a> ios_base::iword

Weist einen als `iword` zu speichernden Wert zu.

```cpp
long& iword(int idx);
```

### <a name="parameters"></a>Parameter

`idx` Der Index des Werts als Speichern einer `iword`.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt einen Verweis auf das Element `idx` des erweiterbaren Arrays mit Elementen des Typ **long** zurück. Alle Elemente sind tatsächlich vorhanden und speichern zunächst den Wert 0. Der zurückgegebene Verweis ist nach dem nächsten Aufruf an `iword` für das Objekt ungültig, nachdem das Objekt durch einen Aufruf an **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt) verändert wurde, oder nachdem es zerstört wurde.

Wenn `idx` negativ ist, oder kein eindeutiger Speicherplatz für das Element zur Verfügung steht, ruft die Funktion [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** auf und gibt möglicherweise einen uneindeutigen Verweis zurück.

Um einen eindeutigen Index für einen Gebrauch für alle Objekte des Typ `ios_base` zu erhalten, rufen Sie [xalloc](#xalloc) auf.

### <a name="example"></a>Beispiel

Unter [xalloc](#xalloc) finden Sie ein Beispiel zur Verwendung von `iword`.

## <a name="openmode"></a> ios_base::openmode

Beschreibt, wie mit einem Stream interagiert wird.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein `bitmask type`, der ein Objekt beschreibt, das den Öffnungsmodus für mehrere iostreams-Objekte speichern kann. Die unterschiedlichen Flagwerte (Elemente) sind:

- **app**, um vor jedem Einfügevorgang bis zum Ende eines Streams zu suchen.

- **ate**, um bis zum Ende eines Streams zu suchen, wenn dessen steuerndes Objekt erstmals erstellt wird.

- **binary**, um eine Datei als binären Stream und nicht als Textstream zu lesen.

- **in** für die Extraktion aus einem Stream.

- **out** für die Einfügung in einen Stream.

- **trunc**, um den Inhalt einer vorhandenen Datei zu löschen, wenn deren steuerndes Objekt erstellt wird.

### <a name="example"></a>Beispiel

```cpp
// ios_base_openmode.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
}
```

## <a name="op_eq"></a> ios_base::operator=

Der Zuweisungsoperator für ios_base-Objekte.

```cpp
ios_base& operator=(const ios_base& right);
```

### <a name="parameters"></a>Parameter

`right` Ein Objekt vom Typ `ios_base`.

### <a name="return-value"></a>Rückgabewert

Das Objekt, an das zugewiesen wird.

### <a name="remarks"></a>Hinweise

Der Operator kopiert die gespeicherte Formatinformation und erstellt gleichzeitig eine Kopie von erweiterbaren Arrays. Dann wird \***this** zurückgegeben. Bitte beachten Sie, dass die Aufrufliste nicht kopiert wird.

Dieser Operator wird nur von `ios_base` abgeleiteten Klassen verwendet.

## <a name="precision"></a> ios_base::precision

Gibt die Anzahl der anzuzeigenden Ziffern in einer Gleitkommazahl an.

```cpp
streamsize precision() const;
streamsize precision(streamsize _Prec);
```

### <a name="parameters"></a>Parameter

`_Prec` Die Anzahl der signifikanten Stellen, um anzuzeigen, oder die Anzahl der Ziffern nach dem Dezimaltrennzeichen in Festkommanotation.

### <a name="return-value"></a>Rückgabewert

Die erste Memberfunktion gibt die gespeicherte [Anzeigegenauigkeit](../standard-library/ios-base-class.md) zurück. Die zweite Memberfunktion speichert `_Prec` in der Anzeigegenauigkeit und gibt den zuletzt gespeicherten Wert zurück.

### <a name="remarks"></a>Hinweise

Gleitkommazahlen werden mit festen Schreibweisen mit [fixed](../standard-library/ios-functions.md#fixed) angezeigt.

### <a name="example"></a>Beispiel

```cpp
// ios_base_precision.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    float i = 31.31234F;

    cout.precision( 3 );
    cout << i << endl;          // display three significant digits
    cout << fixed << i << endl; // display three digits after decimal
                                // point
}
```

```Output
31.3
31.312
```

## <a name="pword"></a> ios_base::pword

Weist einen als `pword` zu speichernden Wert zu.

```cpp
void *& pword(int _Idx);
```

### <a name="parameters"></a>Parameter

`_Idx` Der Index des Werts als Speichern einer `pword`.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt einen Verweis auf das Element _*ldx* des erweiterbaren Arrays mit Elementen des Typs `void` zurück. Alle Elemente sind tatsächlich vorhanden und speichern zunächst den NULL-Zeiger. Der zurückgegebene Verweis ist nach dem nächsten Aufruf an `pword` für das Objekt ungültig, nachdem das Objekt durch einen Aufruf an **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt) verändert wurde, oder nachdem es zerstört wurde.

Wenn _*ldx* negativ ist, oder kein eindeutiger Speicherplatz für das Element zur Verfügung steht, ruft die Funktion [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** auf und gibt möglicherweise einen uneindeutigen Verweis zurück.

Um einen eindeutigen Index für einen Gebrauch für alle Objekte des Typ `ios_base` zu erhalten, rufen Sie [xalloc](#xalloc) auf.

### <a name="example"></a>Beispiel

Unter [xcalloc](#xalloc) finden Sie ein Beispiel für die Verwendung von `pword`.

## <a name="register_callback"></a> ios_base::register_callback

Gibt eine Rückruffunktion an.

```cpp
void register_callback(
    event_callback pfn, int idx);
```

### <a name="parameters"></a>Parameter

`pfn` Ein Zeiger auf die Rückruffunktion.

`idx` Eine benutzerdefinierte Zahl.

### <a name="remarks"></a>Hinweise

Die Memberfunktion schiebt das Paar `{pfn, idx}` im Stapel gespeicherten Rückruf [Rückrufliste](../standard-library/ios-base-class.md). Wenn ein Rückrufereignis **ev** gemeldet wird, die Funktionen werden aufgerufen, in umgekehrter Reihenfolge der Registrierung, der durch den Ausdruck `(*pfn)(ev, *this, idx)`.

### <a name="example"></a>Beispiel

```cpp
// ios_base_register_callback.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void callback1( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback1" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

void callback2( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback2" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

int main( )
{
    // Make sure the imbue will not throw an exception
    // assert( setlocale( LC_ALL, "german" )!=NULL );

    cout.register_callback( callback1, 0 );
    cin.register_callback( callback2, 0 );

    try
    {
        // If no exception because the locale's not found,
        // generate an imbue_event on callback1
        cout.imbue(locale("german"));
    }
    catch(...)
    {
        cout << "exception" << endl;
    }

    // This will
    // (1) erase_event on callback1
    // (2) copyfmt_event on callback2
    cout.copyfmt(cin);

    // We get two erase events from callback2 at the end because
    // both cin and cout have callback2 registered when cin and cout
    // are destroyed at the end of program.
}
```

```Output
in callback1
an imbue event
in callback1
an erase event
in callback2
an copyfmt event
in callback2
an erase event
in callback2
an erase event
```

## <a name="seekdir"></a> ios_base::seekdir

Gibt den Startpunkt für Offsetvorgänge an.

```cpp
namespace std {
    class ios_base {
    public:
        typedef implementation-defined-enumerated-type seekdir;
        static const seekdir beg;
        static const seekdir cur;
        static const seekdir end;
        // ...
    };
}
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein enumerierter Typ, der ein Objekt beschreibt, die den Seek-Modus verwendet als Argument an die Memberfunktionen von mehrere Iostream-Klassen gespeichert werden können. Die unterschiedlichen Flagwerte sind:

- **beg** zur Suche (Ändern der aktuellen Lese- oder Schreibposition), relativ zum Beginn der Sequenz (Array, Stream oder Datei).

- **cur** zur Suche, relativ zur aktuellen Position in der Sequenz.

- **end** zur Suche, relativ zum Ende der Sequenz.

### <a name="example"></a>Beispiel

```cpp
// ios_base_seekdir.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
    file.seekp( 0, ios_base::beg );
    file << "a";
    file.seekp( 0, ios_base::end );
    file << "a";
}
```

## <a name="setf"></a> ios_base::setf

Legt die angegebenen Flags fest.

```cpp
fmtflags setf(
    fmtflags _Mask
);
fmtflags setf(
    fmtflags _Mask,
    fmtflags _Unset
);
```

### <a name="parameters"></a>Parameter

`_Mask` Die Flags zu aktivieren.

*_Unset* die Flags zu deaktivieren.

### <a name="return-value"></a>Rückgabewert

    The previous format flags

### <a name="remarks"></a>Hinweise

    The first member function effectively calls [flags](#flags)(_ *Mask* &#124; \_ *Flags*) (set selected bits) and then returns the previous format flags. The second member function effectively calls **flags**(\_ *Mask* **& fmtfl, flags& ~**`_Mask`) (replace selected bits under a mask) and then returns the previous format flags.

### <a name="example"></a>Beispiel

```cpp
// ios_base_setf.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    int i = 10;
    cout << i << endl;

    cout.unsetf( ios_base::dec );
    cout.setf( ios_base::hex );
    cout << i << endl;

    cout.setf( ios_base::dec );
    cout << i << endl;
    cout.setf( ios_base::hex, ios_base::dec );
    cout << i << endl;
}
```

## <a name="sync_with_stdio"></a> ios_base::sync_with_stdio

Stellt sicher, dass iostream-Vorgänge und Vorgänge der C-Laufzeitbibliothek in der Reihenfolge ausgeführt werden, in der sie im Quellcode stehen.

```cpp
static bool sync_with_stdio(
   bool _Sync = true
);
```

### <a name="parameters"></a>Parameter

`_Sync` Gibt an, ob alle Streams mit synchron sind **Stdio**.

### <a name="return-value"></a>Rückgabewert

    Previous setting for this function.

### <a name="remarks"></a>Hinweise

    The static member function stores a **stdio** sync flag, which is initially **true**. When **true**, this flag ensures that operations on the same file are properly synchronized between the [iostreams](../standard-library/iostreams-conventions.md) functions and those defined in the C++ Standard Library. Otherwise, synchronization may or may not be guaranteed, but performance may be improved. The function stores `_Sync` in the **stdio** sync flag and returns its previous stored value. You can call it reliably only before performing any operations on the standard streams.

## <a name="unsetf"></a> ios_base::unsetf

Bewirkt, dass die angegebenen Flags deaktiviert werden.

```cpp
void unsetf(
   fmtflags _Mask
);
```

### <a name="parameters"></a>Parameter

`_Mask` Die Flags, denen Sie deaktivieren möchten.

### <a name="remarks"></a>Hinweise

    The member function effectively calls [flags](#flags)(`~`*_Mask* **& flags**) (clear selected bits).

### <a name="example"></a>Beispiel

    See [ios_base::setf](#setf) for a sample of using `unsetf`.

## <a name="width"></a> ios_base::width

Legt die Länge des Ausgabestreams fest.

```cpp
streamsize width( ) const;
streamsize width(
   streamsize _Wide
);
```

### <a name="parameters"></a>Parameter

`_Wide` Die gewünschte Größe des ausgabedatenstroms.

### <a name="return-value"></a>Rückgabewert

    The current width setting.

### <a name="remarks"></a>Hinweise

    The first member function returns the stored field width. The second member function stores `_Wide` in the field width and returns its previous stored value.

### <a name="example"></a>Beispiel

```cpp
// ios_base_width.cpp
// compile with: /EHsc
#include <iostream>

int main( ) {
    using namespace std;

    cout.width( 20 );
    cout << cout.width( ) << endl;
    cout << cout.width( ) << endl;
}
```

```Output
20
0
```

## <a name="xalloc"></a> ios_base::xalloc

    Specifies that a variable is part of the stream.

```cpp
static int xalloc( );
```

### <a name="return-value"></a>Rückgabewert

    The static member function returns a stored static value, which it increments on each call.

### <a name="remarks"></a>Hinweise

    You can use the return value as a unique index argument when calling the member functions [iword](#iword) or [pword](#pword).

### <a name="example"></a>Beispiel

```cpp
// ios_base_xalloc.cpp
// compile with: /EHsc
// Lets you store user-defined information.
// iword, jword, xalloc
#include <iostream>

int main( )
{
    using namespace std;

    static const int i = ios_base::xalloc();
    static const int j = ios_base::xalloc();
    cout.iword( i ) = 11;
    cin.iword( i ) = 13;
    cin.pword( j ) = "testing";
    cout << cout.iword( i ) << endl;
    cout << cin.iword( i ) << endl;
    cout << ( char * )cin.pword( j ) << endl;
}
```

```Output
11
13
testing
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
