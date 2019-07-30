---
title: basic_stringbuf-Klasse
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringbuf
- sstream/std::basic_stringbuf::allocator_type
- sstream/std::basic_stringbuf::char_type
- sstream/std::basic_stringbuf::int_type
- sstream/std::basic_stringbuf::off_type
- sstream/std::basic_stringbuf::pos_type
- sstream/std::basic_stringbuf::traits_type
- sstream/std::basic_stringbuf::overflow
- sstream/std::basic_stringbuf::pbackfail
- sstream/std::basic_stringbuf::seekoff
- sstream/std::basic_stringbuf::seekpos
- sstream/std::basic_stringbuf::str
- sstream/std::basic_stringbuf::underflow
helpviewer_keywords:
- std::basic_stringbuf [C++]
- std::basic_stringbuf [C++], allocator_type
- std::basic_stringbuf [C++], char_type
- std::basic_stringbuf [C++], int_type
- std::basic_stringbuf [C++], off_type
- std::basic_stringbuf [C++], pos_type
- std::basic_stringbuf [C++], traits_type
- std::basic_stringbuf [C++], overflow
- std::basic_stringbuf [C++], pbackfail
- std::basic_stringbuf [C++], seekoff
- std::basic_stringbuf [C++], seekpos
- std::basic_stringbuf [C++], str
- std::basic_stringbuf [C++], underflow
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
ms.openlocfilehash: 0445c2f8868fc9f2863ad4a2a12cc00261546c75
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447845"
---
# <a name="basicstringbuf-class"></a>basic_stringbuf-Klasse

Beschreibt einen die Übertragung zu und aus einer Sequenz von in einem Arrayobjekt gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>,
    class Alloc = allocator<Elem>>
class basic_stringbuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parameter

*Zuordnungseinheits*\
Die Zuweisungsklasse.

*Elem*\
Der Typ des grundlegenden Elements der Zeichenfolge.

*Stadtrat*\
Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.

## <a name="remarks"></a>Hinweise

Das Objekt wird reserviert, erweitert und freigegeben, sofern erforderlich, um Änderungen in der Sequenz zu berücksichtigen.

Ein Objekt der Klasse basic_stringbuf< `Elem`, `Tr`, `Alloc`> speichert eine Kopie des Arguments `ios_base::`[openmode](../standard-library/ios-base-class.md#openmode) aus seinem Konstruktor als seinen `stringbuf`-Modus **mode**:

- Wenn `mode & ios_base::in` ungleich 0 ist, kann auf den Eingabepuffer zugegriffen werden. Weitere Informationen finden Sie unter [basic_streambuf-Klasse](../standard-library/basic-streambuf-class.md).

- Wenn `mode & ios_base::out` ungleich 0 ist, kann auf den Ausgabepuffer zugegriffen werden.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_stringbuf](#basic_stringbuf)|Konstruiert ein Objekt vom Typ `basic_stringbuf`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Der Typ ist ein Synonym für den Vorlagen Parameter " *Zuweisung*".|
|[char_type](#char_type)|Verknüpft einen Typnamen mit dem Vorlagenparameter *Elem*.|
|[int_type](#int_type)|Macht diesen Typ innerhalb `basic_filebuf`des Gültigkeits Bereichs, der dem Typ desselben Namens im *TR* -Bereich entspricht.|
|[off_type](#off_type)|Macht diesen Typ innerhalb `basic_filebuf`des Gültigkeits Bereichs, der dem Typ desselben Namens im *TR* -Bereich entspricht.|
|[pos_type](#pos_type)|Macht diesen Typ innerhalb `basic_filebuf`des Gültigkeits Bereichs, der dem Typ desselben Namens im *TR* -Bereich entspricht.|
|[traits_type](#traits_type)|Verknüpft einen Typnamen mit dem *Tr*-Vorlagenparameter.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[overflow](#overflow)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|
|[pbackfail](#pbackfail)|Die geschützte virtuelle Memberfunktion versucht, ein Element zurück in den Eingabepuffer zu versetzen und es dann zum aktuellen Element zu ernennen (wird mit dem nächsten Zeiger darauf gezeigt).|
|[seekoff](#seekoff)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|
|[seekpos](#seekpos)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|
|[str](#str)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|
|swap||
|[underflow](#underflow)|Die geschützte virtuelle Memberfunktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.|

## <a name="requirements"></a>Anforderungen

**Header:** \<sstream>

**Namespace:** std

## <a name="allocator_type"></a> basic_stringbuf::allocator_type

Der Typ ist ein Synonym für den Vorlagen Parameter " *Zuweisung*".

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringbuf"></a> basic_stringbuf::basic_stringbuf

Konstruiert ein Objekt vom Typ `basic_stringbuf`.

```cpp
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Mode*\
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*SRT*\
Ein Objekt vom Typ [basic_string](../standard-library/basic-string-class.md).

### <a name="remarks"></a>Hinweise

Der erste Konstruktor speichert einen NULL-Zeiger in allen Zeigern, die den Eingabe- und Ausgabepuffer steuern. Weitere Informationen finden Sie im Abschnitt „Hinweise“ unter [basic_streambuf-Klasse](../standard-library/basic-streambuf-class.md). Außerdem speichert Sie *_Mode* als Stringbuf-Modus. Weitere Informationen finden Sie im Abschnitt „Hinweise“ unter [basic_stringbuf-Klasse](../standard-library/basic-stringbuf-class.md).

Der zweite Konstruktor ordnet eine Kopie der Sequenz zu, die vom Zeichen folgen Objekt *Str*gesteuert wird. Wenn `_Mode & ios_base::in` ungleich null ist, wird festgelegt, dass der Eingabepuffer den Lesevorgang am Anfang der Sequenz beginnt. Wenn `_Mode & ios_base::out` ungleich null ist, wird festgelegt, dass der Ausgabepuffer den Schreibvorgang am Anfang der Sequenz beginnt. Außerdem speichert Sie *_Mode* als Stringbuf-Modus. Weitere Informationen finden Sie im Abschnitt „Hinweise“ unter [basic_stringbuf-Klasse](../standard-library/basic-stringbuf-class.md).

## <a name="char_type"></a> basic_stringbuf::char_type

Verknüpft einen Typnamen mit dem Vorlagenparameter *Elem*.

```cpp
typedef Elem char_type;
```

## <a name="int_type"></a> basic_stringbuf::int_type

Legt diesen Typ innerhalb des basic_filebuf's-Bereichs entsprechend dem Typ desselben Namens im `Tr` Bereich ab.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="off_type"></a> basic_stringbuf::off_type

Legt diesen Typ innerhalb des basic_filebuf's-Bereichs entsprechend dem Typ desselben Namens im `Tr` Bereich ab.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="overflow"></a> basic_stringbuf::overflow

Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parameter

*_Meta*\
Das Zeichen, das in den Puffer eingefügt werden soll, oder `traits_type::eof`.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `traits_type::eof` zurückgegeben. Andernfalls wird **traits_type::** [not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) zurückgegeben.

### <a name="remarks"></a>Hinweise

*Wenn\_Meta* nicht gleich **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)ist, versucht die Funktion des geschützten virtuellen Members, das Element **traits_type::** [To_char_type](../standard-library/char-traits-struct.md#to_char_type)( *\_Meta*) in den Ausgabepuffer. Hierfür gibt es verschiedene Möglichkeiten:

- Wenn eine Schreibposition verfügbar ist, kann das Element in der Schreibposition gespeichert werden, und der nächste Zeiger für den Ausgabepuffer kann inkrementiert werden.

- Eine Schreibposition kann verfügbar gemacht werden, indem neuer oder zusätzlicher Speicher für den Ausgabepuffer zugewiesen wird. Das Erweitern des Ausgabepuffers erweitert so auch alle zugewiesenen Eingabepuffer.

## <a name="pbackfail"></a> basic_stringbuf::pbackfail

Die geschützte virtuelle Memberfunktion versucht, ein Element zurück in den Eingabepuffer zu versetzen, und es dann zum aktuellen Element zu ernennen (wird mit dem nächsten Zeiger darauf gezeigt).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parameter

*_Meta*\
Das Zeichen, das in den Puffer eingefügt werden soll, oder `traits_type::eof`.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `traits_type::eof` zurückgegeben. Andernfalls wird **traits_type::** [not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) zurückgegeben.

### <a name="remarks"></a>Hinweise

Wenn *_Meta* gleich **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)ist, handelt es sich bei dem Element, das zurückgesendet werden soll, tatsächlich um das Element, das sich bereits vor dem aktuellen Element im Stream befindet. Andernfalls wird dieses Element durch **byte** = **traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *Meta*) ersetzt. Ein Element kann auf verschiedene Arten durch die Funktion wiederhergestellt werden:

- Wenn eine Position zur Wiederherstellung verfügbar ist, und das Element, das dort gespeichert ist, „byte“ entspricht, kann der nächste Zeiger für den Eingabepuffer verringert werden.

- Wenn eine Position zur Wiederherstellung verfügbar ist, und der stringbuf-Modus zulässt, dass die Sequenz geändert wird ( **mode & ios_base::out** ist ungleich null), kann „byte“ in der Position zur Wiederherstellung gespeichert werden und den nächsten Zeiger für den Eingabepuffer verringern.

## <a name="pos_type"></a> basic_stringbuf::pos_type

Legt diesen Typ innerhalb des basic_filebuf's-Bereichs entsprechend dem Typ desselben Namens im `Tr` Bereich ab.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a> basic_stringbuf::seekoff

Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Off*\
Die Position, die relativ zu *_Way*gesucht werden soll. Weitere Informationen finden Sie unter [basic_stringbuf::off_type](#off_type).

*_Way*\
Gibt den Startpunkt für Offsetvorgänge an. Mögliche Werte sind unter [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) aufgeführt.

*_Mode*\
Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden. Weitere Informationen finden Sie unter [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

### <a name="return-value"></a>Rückgabewert

Gibt die neue Position oder eine ungültige Streamposition zurück.

### <a name="remarks"></a>Hinweise

Für ein Objekt der Klasse `basic_stringbuf<Elem, Tr, Alloc>` besteht eine Streamposition nur aus einem Streamoffset. Das Offset Null legt das erste Element der kontrollierten Sequenz fest.

Die neue Position wird wie folgt bestimmt:

- Wenn `_Way` der == Wertist, ist die neue Position der Anfang des Streams Plus *_Off.* `ios_base::beg`

- Wenn `_Way` der == Wertist, ist die neue Position die aktuelle Streamposition Plus *_Off.* `ios_base::cur`

- Wenn `_Way` der == Wertist, ist die neue Position das Ende des Streams Plus *_Off.* `ios_base::end`

Wenn `_Mode & ios_base::in` ungleich null ist, ändert die Funktion die nächste Position, die im Eingabepuffer gelesen werden soll. Wenn `_Mode & ios_base::out` ungleich null ist, ändert die Funktion die nächste Position, die im Ausgabepuffer gelesen werden soll. Damit ein Stream betroffen wird, muss ein Puffer bestehen. Damit eine Positionierung erfolgreich ist, muss die resultierende Streamposition innerhalb der kontrollierten Sequenz liegen. Wenn sich die Funktion auf beide streampositionen auswirkt, muss `ios_base::beg` *_Way* `ios_base::end` oder lauten, und beide Streams werden am gleichen Element positioniert. Andernfalls (oder wenn keine Position betroffen ist) tritt bei der Positionierung ein Fehler ein.

Wenn die Funktion erfolgreich eine der beiden Streampositionen ändern kann, gibt sie die resultierende Streamposition zurück. Andernfalls schlägt sie fehl und gibt eine ungültige Streamposition zurück.

## <a name="seekpos"></a> basic_stringbuf::seekpos

Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Sp*\
Die Position, nach der gesucht werden soll.

*_Mode*\
Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich eine der beiden Streampositionen ändern kann, gibt sie die resultierende Streamposition zurück. Andernfalls schlägt sie fehl und gibt eine ungültige Streamposition zurück. Vergleichen Sie den Rückgabewert mit `pos_type(off_type(-1))`, um festzustellen, ob die Streamposition ungültig ist.

### <a name="remarks"></a>Hinweise

Für ein Objekt der Klasse basic_stringbuf< **Elem**, **Tr**, `Alloc`> besteht eine Streamposition bloß aus einem Streamoffset. Das Offset Null legt das erste Element der gesteuerten Sequenz fest. Die neue Position wird von _ *Sp* bestimmt.

Wenn **mode & ios_base::in** ungleich null ist, ändert die Funktion die nächste Position, die in den Eingabepuffer gelesen werden soll. Wenn **mode & ios_base::out** ungleich null ist, ändert die Funktion die nächste Position, die in den Ausgabepuffer geschrieben werden soll. Damit ein Stream betroffen wird, muss ein Puffer bestehen. Damit eine Positionierung erfolgreich ist, muss die resultierende Streamposition innerhalb der gesteuerten Sequenz liegen. Andernfalls (oder wenn keine Position betroffen ist) tritt bei der Positionierung ein Fehler ein.

## <a name="str"></a> basic_stringbuf::str

Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.

```cpp
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parameter

*_Newstr*\
Die neue Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Gibt ein Objekt der Klasse [basic_string](../standard-library/basic-string-class.md)\< **Elem**, **Tr**, Alloc **>,** zurück, dessen gesteuerte Sequenz eine Kopie der von **\*this** gesteuerten Sequenz ist.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion gibt ein Objekt der Klasse basic_string< **Elem**, **Tr**, `Alloc`> zurück, dessen gesteuerte Sequenz eine Kopie der von **\*this** gesteuerten Sequenz ist. Die kopierte Sequenz ist vom Modus „stored stringbuf“ abhängig:

- Wenn **mode & ios_base::out** ungleich null ist, und ein Ausgabepuffer besteht, ist die Sequenz der gesamte Ausgabepuffer ( [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase)-Elemente, die mit `pbase` beginnen).

- Wenn **mode & ios_base::in** ungleich null ist, und ein Eingabepuffer besteht, ist die Sequenz der gesamte Eingabepuffer ( [egptr](../standard-library/basic-streambuf-class.md#egptr) - [back](../standard-library/basic-streambuf-class.md#eback)-Elemente, die mit `eback` beginnen).

- Andernfalls ist die kopierte Sequenz leer.

Die zweite Memberfunktion gibt alle Sequenzen frei, die von **\*this** kontrolliert werden. Anschließend wird eine von *_Newstr*gesteuerte Kopie der Sequenz zugeordnet. Wenn **mode & ios_base::in** ungleich null ist, wird festgelegt, dass der Eingabepuffer den Lesevorgang am Anfang der Sequenz beginnt. Wenn **mode & ios_base::out** ungleich null ist, wird festgelegt, dass der Ausgabepuffer den Schreibvorgang am Anfang der Sequenz beginnt.

### <a name="example"></a>Beispiel

```cpp
// basic_stringbuf_str.cpp
// compile with: /EHsc
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   basic_string<char> i( "test" );
   stringstream ss;

   ss.rdbuf( )->str( i );
   cout << ss.str( ) << endl;

   ss << "z";
   cout << ss.str( ) << endl;

   ss.rdbuf( )->str( "be" );
   cout << ss.str( ) << endl;
}
```

```Output
test
zest
be
```

## <a name="traits_type"></a> basic_stringbuf::traits_type

Verknüpft einen Typnamen mit dem *Tr*-Vorlagenparameter.

```cpp
typedef Tr traits_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter *Tr* dar.

## <a name="underflow"></a> basic_stringbuf::underflow

Die geschützte virtuelle Funktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird **traits_type::** [eof](../standard-library/char-traits-struct.md#eof) zurückgegeben. Andernfalls wird das aktuelle Element, das konvertiert wurde, in den Eingabestream zurückgegeben.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Member-Funktion versucht, das aktuelle Element `byte` aus dem Eingabepuffer zu extrahieren, die aktuelle Streamposition fortzusetzen und das Element als **traits_type::** [To_int_type](../standard-library/char-traits-struct.md#to_int_type)( **Byte**) zurückzugeben. Dies kann auf eine Weise durchzuführen sein: Wenn eine Lese Position verfügbar ist, nimmt `byte` Sie als das an der Lese Position gespeicherte Element an und verschiebt den nächsten Zeiger für den Eingabepuffer.

## <a name="swap"></a> basic_streambuf::swap

Vertauscht den Inhalt dieses Zeichenfolgenpuffers mit einem anderen Zeichenfolgenpuffer.

```cpp
void basic_stringbuf<T>::swap(basic_stringbuf& other)
```

### <a name="parameters"></a>Parameter

*außer*\
Der „basic_stringbuf“, dessen Inhalt mit diesem „basic_stringbuf“ getauscht wird.

### <a name="remarks"></a>Hinweise

## <a name="op_eq"></a> basic_stringbuf::operator=

Weist den Inhalt von basic_stringbuf auf der rechten Seite des Operators dem basic_stringbuf auf der linken Seite zu.

```cpp
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)
```

### <a name="parameters"></a>Parameter

*außer*\
Ein basic_stringbuf, dessen Inhalt, einschließlich Gebietsschema-Merkmalen, dem Stringbuf auf der linken Seite des Operators zugewiesen wird.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
