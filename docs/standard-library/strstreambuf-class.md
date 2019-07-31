---
title: strstreambuf-Klasse
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstreambuf::freeze
- strstream/std::strstreambuf::overflow
- strstream/std::strstreambuf::pbackfail
- strstream/std::strstreambuf::pcount
- strstream/std::strstreambuf::seekoff
- strstream/std::strstreambuf::seekpos
- strstream/std::strstreambuf::str
- strstream/std::strstreambuf::underflow
helpviewer_keywords:
- std::strstreambuf [C++], freeze
- std::strstreambuf [C++], overflow
- std::strstreambuf [C++], pbackfail
- std::strstreambuf [C++], pcount
- std::strstreambuf [C++], seekoff
- std::strstreambuf [C++], seekpos
- std::strstreambuf [C++], str
- std::strstreambuf [C++], underflow
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
ms.openlocfilehash: f24d8fe99bc211e026172e42669cf5e430ad31e8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459074"
---
# <a name="strstreambuf-class"></a>strstreambuf-Klasse

Beschreibt einen Streampuffer, der die Übertragung von Elementen in eine und aus einer Sequenz von Elementen steuert, die in einem **char** -Array Objekt gespeichert sind.

## <a name="syntax"></a>Syntax

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Hinweise

Je nachdem, wie das Objekt aufgebaut ist, kann es nach Bedarf reserviert, erweitert und freigegeben werden, um Änderungen in der Sequenz zu berücksichtigen.

Ein aus der Klasse `strstreambuf` abgeleitetes Objekt speichert mehrere Bits mit Modusinformationen als seinen `strstreambuf`-Modus. Diese Bits geben an, ob Folgendes für die gesteuerte Sequenz zutrifft:

- Sie wurde reserviert und muss schließlich freigegeben werden.

- Sie kann geändert werden.

- Sie kann durch erneute Reservierung von Speicher erweitert werden.

- Sie wurde eingefroren und muss daher „aufgetaut“ werden, bevor das Objekt zerstört wird, oder sie muss (sofern reserviert) durch ein Element freigegeben werden, das nicht mit dem Objekt identisch ist.

Eine gesteuerte Sequenz, die eingefroren ist, kann weder geändert noch erweitert werden, unabhängig vom Status dieser einzelnen Modusbits.

Das Objekt speichert auch Zeiger auf zwei Funktionen, mit denen die `strstreambuf`-Speicherbelegung gesteuert wird. Sind diese Zeiger NULL-Zeiger, muss für das Objekt eine eigene Methode des Belegens und Freigebens von Speicher für die gesteuerte Sequenz formuliert sein.

> [!NOTE]
> Diese Klasse ist veraltet. Verwenden Sie stattdessen [stringbuf](../standard-library/sstream-typedefs.md#stringbuf) oder [wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[strstreambuf](#strstreambuf)|Konstruiert ein Objekt vom Typ `strstreambuf`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[freeze](#freeze)|Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.|
|[overflow](#overflow)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|
|[pbackfail](#pbackfail)|Eine geschützte virtuelle Memberfunktion, die versucht, ein Element in den Eingabestreams zurückzuschreiben, und es dann zum aktuellen Element macht (auf das der nächste Zeiger zeigt).|
|[pcount](#pcount)|Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.|
|[seekoff](#seekoff)|Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|
|[seekpos](#seekpos)|Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|
|[str](#str)|Ruft [freeze](#freeze) auf und gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|
|[underflow](#underflow)|Eine geschützte virtuelle Funktion zum Extrahieren des aktuellen Elements aus dem Eingabestream.|

## <a name="requirements"></a>Anforderungen

**Header:** \<strstream>

**Namespace:** std

## <a name="freeze"></a> strstreambuf::freeze

Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parameter

*_Freezeit*\
Ein boolescher Wert, der angibt, ob der Stream eingefroren werden soll.

### <a name="remarks"></a>Hinweise

Wenn *_Freezeit* den Wert true hat, ändert die Funktion `strstreambuf` den gespeicherten Modus, damit die gesteuerte Sequenz fixiert wird. Andernfalls ist es die kontrollierte Sequenz nicht fixiert.

[str](#str) impliziert `freeze`.

> [!NOTE]
> Ein fixierter Puffer wird während der `strstreambuf`-Zerstörung nicht freigegeben. Sie müssen die Fixierung des Puffers aufheben, bevor er freigegeben wird, um einen Speicherverlust zu vermeiden.

### <a name="example"></a>Beispiel

```cpp
// strstreambuf_freeze.cpp
// compile with: /EHsc

#include <iostream>
#include <strstream>

using namespace std;

void report(strstream &x)
{
    if (!x.good())
        cout << "stream bad" << endl;
    else
        cout << "stream good" << endl;
}

int main()
{
    strstream x;

    x << "test1";
    cout << "before freeze: ";
    report(x);

    // Calling str freezes stream.
    cout.write(x.rdbuf()->str(), 5) << endl;
    cout << "after freeze: ";
    report(x);

    // Stream is bad now, wrote on frozen stream
    x << "test1.5";
    cout << "after write to frozen stream: ";
    report(x);

    // Unfreeze stream, but it is still bad
    x.rdbuf()->freeze(false);
    cout << "after unfreezing stream: ";
    report(x);

    // Clear stream
    x.clear();
    cout << "after clearing stream: ";
    report(x);

    x << "test3";
    cout.write(x.rdbuf()->str(), 10) << endl;

    // Clean up.  Failure to unfreeze stream will cause a
    // memory leak.
    x.rdbuf()->freeze(false);
}
```

```Output
before freeze: stream good
test1
after freeze: stream good
after write to frozen stream: stream bad
after unfreezing stream: stream bad
after clearing stream: stream good
test1test3
```

## <a name="overflow"></a> strstreambuf::overflow

Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Parameter

*_Meta*\
Das Zeichen, das in den Puffer eingefügt werden soll, oder `EOF`.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `EOF` zurückgegeben. Andernfalls wird bei  *\_Meta* ==  `EOF`einandererWertalszurückgegeben.`EOF` Andernfalls wird  *\_Meta*zurückgegeben.

### <a name="remarks"></a>Hinweise

`EOF`Wenn  *\_Meta* ! =, versucht die Funktion des geschützten virtuellen Members, das Element `(char)_Meta` in den Ausgabepuffer einzufügen. Hierfür gibt es verschiedene Möglichkeiten:

- Wenn eine Schreibposition verfügbar ist, kann das Element in der Schreibposition gespeichert werden, und der nächste Zeiger für den Ausgabepuffer kann inkrementiert werden.

- Wenn der gespeicherte strstreambuf Modus anzeigt, dass die kontrollierte Sequenz änderbar, erweiterbar und nicht fixiert ist, kann die Funktion eine Schreibposition verfügbar machen, indem für den Ausgabepuffer eine neue zugewiesen wird. Das Erweitern des Ausgabepuffers erweitert auf diese Weise auch alle zugewiesenen Eingabepuffer.

## <a name="pbackfail"></a> strstreambuf::pbackfail

Eine geschützte virtuelle Memberfunktion, die versucht, ein Element in den Eingabestreams zurückzuschreiben, und es dann zum aktuellen Element macht (auf das der nächste Zeiger zeigt).

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Parameter

*_Meta*\
Das Zeichen, das in den Puffer eingefügt werden soll, oder `EOF`.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `EOF` zurückgegeben. Andernfalls wird bei  *\_Meta* ==  `EOF`einandererWertalszurückgegeben.`EOF` Andernfalls wird  *\_Meta*zurückgegeben.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, ein Element im Eingabepuffer wiederherzustellen und es dann zum aktuellen Element zu machen (der nächste Zeiger zeigt auf das Element).

*Wenn\_Meta*,istdas`EOF`Element, das zurück abgelegt werden soll, das, das sich bereits vor dem aktuellen Element im Stream befindet. ==  Andernfalls wird dieses Element durch `ch = (char)_Meta`ersetzt. Ein Element kann auf verschiedene Arten durch die Funktion wiederhergestellt werden:

- Wenn eine rückgabeposition verfügbar ist und das Element, das dort gespeichert ist `ch`, gleich ist, kann der nächste Zeiger für den Eingabepuffer verringert werden.

- Wenn eine Position für die Wiederherstellung verfügbar ist und der Modus "straustreambuf" besagt, dass die gesteuerte Sequenz geändert werden kann, `ch` kann die Funktion in der Putback-Position speichern und den nächsten Zeiger für den Eingabepuffer verringern.

## <a name="pcount"></a> strstreambuf::pcount

Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zähler der Anzahl von Elementen, die in die kontrollierte Sequenz geschrieben wurden.

### <a name="remarks"></a>Hinweise

Wenn [pptr](../standard-library/basic-streambuf-class.md#pptr) ein NULL-Zeiger ist, gibt die Funktion null zurück. Andernfalls wird " `pptr` [pbase](../standard-library/basic-streambuf-class.md#pbase)" zurück  - gegeben.

### <a name="example"></a>Beispiel

```cpp
// strstreambuf_pcount.cpp
// compile with: /EHsc
#include <iostream>
#include <strstream>
using namespace std;

int main( )
{
   strstream x;
   x << "test1";
   cout << x.rdbuf( )->pcount( ) << endl;
   x << "test2";
   cout << x.rdbuf( )->pcount( ) << endl;
}
```

## <a name="seekoff"></a> strstreambuf::seekoff

Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Off*\
Die Position, die relativ zu *_Way*gesucht werden soll.

*_Way*\
Gibt den Startpunkt für Offsetvorgänge an. Mögliche Werte sind unter [seekdir](../standard-library/ios-base-class.md#seekdir) aufgeführt.

*_Which*\
Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion eine der beiden Streampositionen erfolgreich ändert, gibt sie die resultierende Streamposition zurück. Andernfalls schlägt sie fehl und gibt eine ungültige Streamposition zurück.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern. Für ein Objekt der Klasse strstreambuf besteht eine Streamposition lediglich aus einem Streamoffset. Das Offset null legt das erste Element der kontrollierten Sequenz fest.

Die neue Position wird wie folgt bestimmt:

- Wenn `_Way == ios_base::beg`der Wert ist, ist die neue Position der Anfang des Streams Plus *_Off*.

- Wenn `_Way == ios_base::cur`der Wert ist, ist die neue Position die aktuelle Streamposition Plus *_Off*.

- Wenn `_Way == ios_base::end`der Wert ist, ist die neue Position das Ende des Streams Plus *_Off*.

Wenn `_Which & ios_base::in` ungleich 0 (null) ist und der Eingabepuffer vorhanden ist, ändert die Funktion die nächste Position, die im Eingabepuffer gelesen werden soll. Wenn `_Which & ios_base::out` auch ungleich NULL ist, `_Way != ios_base::cur`und der Ausgabepuffer vorhanden ist, legt die Funktion auch die nächste zu schreibende Position fest, damit Sie der nächsten zu lesenden Position entspricht.

Wenn `_Which & ios_base::out` andernfalls ungleich 0 (null) ist und der Ausgabepuffer vorhanden ist, ändert die Funktion die nächste Position, die in den Ausgabepuffer geschrieben werden soll. Andernfalls schlägt der Positionierungsvorgang fehl. Damit eine Positionierung erfolgreich ist, muss die resultierende Streamposition innerhalb der kontrollierten Sequenz liegen.

## <a name="seekpos"></a> strstreambuf::seekpos

Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Sp*\
Die Position, nach der gesucht werden soll.

*_Which*\
Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion eine der beiden Streampositionen erfolgreich ändert, gibt sie die resultierende Streamposition zurück. Andernfalls schlägt sie fehl und gibt eine ungültige Streamposition zurück. Vergleichen Sie den Rückgabewert mit `pos_type(off_type(-1))`, um festzustellen, ob die Streamposition ungültig ist.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern. Für ein Objekt der Klasse strstreambuf besteht eine Streamposition lediglich aus einem Streamoffset. Das Offset null legt das erste Element der kontrollierten Sequenz fest. Die neue Position wird von *_Sp*bestimmt.

Wenn `_Which` & **ios_base::in** ungleich null ist, ändert die Funktion die nächste Position, die im Eingabepuffer gelesen werden soll. Wenn `_Which` & `ios_base::out` ungleich null und der Ausgabepuffer vorhanden ist, legt die Funktion auch die nächste zu schreibende Position so fest, dass sie der nächsten zu lesenden Position entspricht. Ansonsten ändert die Funktion die nächste Position, die im Ausgabepuffer geschrieben werden soll, wenn `_Which` & `ios_base::out` ungleich null ist. Andernfalls schlägt der Positionierungsvorgang fehl. Damit eine Positionierung erfolgreich ist, muss die resultierende Streamposition innerhalb der kontrollierten Sequenz liegen.

## <a name="str"></a> strstreambuf::str

Ruft [freeze](#freeze) auf und gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.

```cpp
char *str();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den Anfang der kontrollierten Sequenz.

### <a name="remarks"></a>Hinweise

Kein abschließendes Null-Element vorhanden, sofern Sie nicht explizit ein Element einfügen.

### <a name="example"></a>Beispiel

Unter [strstreambuf::freeze](#freeze) finden Sie ein Beispiel, das **str** verwendet.

## <a name="strstreambuf"></a> strstreambuf::strstreambuf

Konstruiert ein Objekt vom Typ `strstreambuf`.

```cpp
explicit strstreambuf(streamsize count = 0);

strstreambuf(void (* _Allocfunc)(size_t),
    void (* _Freefunc)(void*));

strstreambuf(char* _Getptr,
    streamsize count,
    char* _Putptr = 0);

strstreambuf(signed char* _Getptr,
    streamsize count,
    signed char* _Putptr = 0);

strstreambuf(unsigned char* _Getptr,
    streamsize count,
    unsigned char* _Putptr = 0);

strstreambuf(const char* _Getptr,
    streamsize count);

strstreambuf(const signed char* _Getptr,
    streamsize count);

strstreambuf(const unsigned char* _Getptr,
    streamsize count);
```

### <a name="parameters"></a>Parameter

*_Allocfunc*\
Funktion, mit der Speicher zugewiesen wird.

*Countdown*\
Bestimmt die Länge des Puffers, auf den von *_Getptr*verwiesen wird. Wenn *_Getptr* kein Argument (erstes konstruktorformular) ist, wird eine vorgeschlagene Zuordnungs Größe für die Puffer angezeigt.

*_Freefunc*\
Zum Freigeben von Pufferspeicher verwendete Funktion.

*_Getptr*\
Ein Puffer, der für die Eingabe verwendet wird.

*_Putptr*\
Ein Puffer, der für die Ausgabe verwendet wird.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor speichert einen NULL-Zeiger in allen Zeigern, die den Eingabepuffer, den Ausgabepuffer und die strstreambuf-Zuweisung steuern. Legt den strstreambuf-Modus so fest, dass die kontrollierte Sequenz änderbar und erweiterbar ist. Außerdem wird die *Anzahl* als vorgeschlagene anfängliche Zuordnungs Größe akzeptiert.

Der zweite Konstruktor verhält sich wie der erste, mit der Ausnahme, dass er  *\_allocfunc* als Zeiger auf die Funktion speichert, die aufruft, um Speicher und  *\_freefunc* als Zeiger auf die Funktion zuzuordnen, die aufgerufen werden soll, um diesen Speicher freizugeben.

Die drei Konstruktoren:

```cpp
strstreambuf(char *_Getptr,
    streamsize count,
    char *putptr = 0);

strstreambuf(signed char *_Getptr,
    streamsize count,
    signed char *putptr = 0);

strstreambuf(unsigned char *_Getptr,
    streamsize count,
    unsigned char *putptr = 0);
```

verhalten sich wie der erste, außer dass `_Getptr` das Arrayobjekt festlegt, das die kontrollierte Sequenz enthält. (Daher darf es kein NULL-Zeiger sein.) Die Anzahl der Elemente *N* im Array wird wie folgt bestimmt:

- Wenn (`count` > 0), dann ist `count`N.

- Wenn (`count` = = 0), dann ist `strlen`N (( **konstant** `char` *) `_Getptr` ).

- Wenn (`count` < 0), dann ist N **INT_MAX**.

Wenn `_Putptr` ein NULL-Zeiger ist, legt die Funktion nur einen Eingabepuffer fest indem sie Folgendes ausführt:

```cpp
setg(_Getptr,
    _Getptr,
    _Getptr + N);
```

Andernfalls legt die Eingabe- und Ausgabepuffer fest, indem sie Folgendes ausführt:

```cpp
setg(_Getptr,
    _Getptr,
    _Putptr);

setp(_Putptr,
    _Getptr + N);
```

In diesem Fall muss `_Putptr` im Intervall [ `_Getptr`, `_Getptr`  +  *N*] liegen.

Die drei Konstruktoren:

```cpp
strstreambuf(const char *_Getptr,
    streamsize count);

strstreambuf(const signed char *_Getptr,
    streamsize count);

strstreambuf(const unsigned char *_Getptr,
    streamsize count);
```

verhalten sich wie:

```cpp
streambuf((char *)_Getptr, count);
```

abgesehen davon, dass der gespeicherte Modus die kontrollierte Sequenz weder änderbar noch erweiterbar macht.

## <a name="underflow"></a> strstreambuf::underflow

Eine geschützte virtuelle Funktion zum Extrahieren des aktuellen Elements aus dem Eingabestream.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `EOF` zurückgegeben. Andernfalls wird das aktuelle Element, wie zuvor beschrieben, konvertiert in den Eingabestream zurückgegeben.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Member-Funktion versucht, das aktuelle Element `ch` aus dem Eingabepuffer zu extrahieren, dann die aktuelle Streamposition fortzusetzen und das Element als`int`()`unsigned char`() **ch**zurückzugeben. Dies ist nur eine Möglichkeit: Wenn eine Lese Position verfügbar ist, wird Sie als das an `ch` der Lese Position gespeicherte Element benötigt und der nächste Zeiger für den Eingabepuffer erhöht.

## <a name="see-also"></a>Siehe auch

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
