---
title: basic_filebuf-Klasse
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_filebuf
- fstream/std::basic_filebuf::char_type
- fstream/std::basic_filebuf::int_type
- fstream/std::basic_filebuf::off_type
- fstream/std::basic_filebuf::pos_type
- fstream/std::basic_filebuf::traits_type
- fstream/std::basic_filebuf::close
- fstream/std::basic_filebuf::is_open
- fstream/std::basic_filebuf::open
- fstream/std::basic_filebuf::overflow
- fstream/std::basic_filebuf::pbackfail
- fstream/std::basic_filebuf::seekoff
- fstream/std::basic_filebuf::seekpos
- fstream/std::basic_filebuf::setbuf
- fstream/std::basic_filebuf::Swap
- fstream/std::basic_filebuf::sync
- fstream/std::basic_filebuf::uflow
- fstream/std::basic_filebuf::underflow
helpviewer_keywords:
- std::basic_filebuf [C++]
- std::basic_filebuf [C++], char_type
- std::basic_filebuf [C++], int_type
- std::basic_filebuf [C++], off_type
- std::basic_filebuf [C++], pos_type
- std::basic_filebuf [C++], traits_type
- std::basic_filebuf [C++], close
- std::basic_filebuf [C++], is_open
- std::basic_filebuf [C++], open
- std::basic_filebuf [C++], overflow
- std::basic_filebuf [C++], pbackfail
- std::basic_filebuf [C++], seekoff
- std::basic_filebuf [C++], seekpos
- std::basic_filebuf [C++], setbuf
- std::basic_filebuf [C++], Swap
- std::basic_filebuf [C++], sync
- std::basic_filebuf [C++], uflow
- std::basic_filebuf [C++], underflow
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
ms.openlocfilehash: fcf673d8e6d871a7920150b5f62fd3d62135b52c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500528"
---
# <a name="basicfilebuf-class"></a>basic_filebuf-Klasse

Beschreibt einen Streampuffer, der die Übertragung von Elementen des Typs steuert *Elem*, dessen Zeichenmerkmale von der Klasse ermittelt werden *Tr*zu und aus einer Sequenz von Elementen in einer externen Datei gespeichert.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_filebuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parameter

*Elem*<br/>
Das grundlegende Element des Dateipuffers.

*Tr*<br/>
Die Merkmale des grundlegenden Elements des Dateipuffers (in der Regel `char_traits`< `Elem`>).

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt einen Streampuffer, der steuert, wie Elemente des Typs *Elem*, dessen Zeichenmerkmale durch die Klasse *Tr* bestimmt sind, in eine oder aus einer Sequenz von Elementen übertragen werden, die in einer externen Datei gespeichert sind.

> [!NOTE]
> Objekte des Typs `basic_filebuf` werden erstellt, mit einem internen Puffer des Typs `char *` unabhängig von der `char_type` durch den Typparameter angegebene *Elem*. Dies bedeutet, dass eine Unicode-Zeichenfolge (mit **"wchar_t"** Zeichen) wird in eine ANSI-Zeichenfolge konvertiert werden (mit **Char** Zeichen) bevor sie auf den internen Puffer geschrieben werden. Erstellen Sie zum Speichern von Unicode-Zeichenfolgen im Puffer einen neuen Puffer des Typs **"wchar_t"** und legen Sie es mit der [basic_streambuf:: pubsetbuf](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` Methode. Ein Beispiel, in dem dieses Verhalten veranschaulicht wird, finden Sie im Folgenden.

Ein Objekt der Klasse`basic_filebuf`< `Elem`, `Tr`> speichert einen Dateizeiger, der das `FILE`-Objekt angibt, welches den mit einer geöffneten Datei verknüpften Stream steuert. Es speichert zudem Zeiger zu zwei Dateikonvertierungs-Facets für die Verwendung durch die geschützten Memberfunktionen [overflow](#overflow) und [underflow](#underflow). Weitere Informationen finden Sie unter [basic_filebuf::open](#open).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie ein Objekt des Typs `basic_filebuf<wchar_t>` gezwungen wird, Unicode-Zeichen in seinem internen Puffer durch den Aufruf der `pubsetbuf()`-Methode zu speichern.

```cpp
// unicode_basic_filebuf.cpp
// compile with: /EHsc

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>
#include <memory.h>
#include <string.h>

#define IBUFSIZE 16

using namespace std;

void hexdump(const string& filename);

int main()
{
    wchar_t* wszHello = L"Hello World";
    wchar_t wBuffer[128];

    basic_filebuf<wchar_t> wOutFile;

    // Open a file, wcHello.txt, then write to it, then dump the
    // file's contents in hex
    wOutFile.open("wcHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wcHello.txt\n";
        return -1;
    }
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";
    hexdump(string("wcHello.txt"));

    // Open a file, wwHello.txt, then set the internal buffer of
    // the basic_filebuf object to be of type wchar_t, then write
    // to the file and dump the file's contents in hex
    wOutFile.open("wwHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wwHello.txt\n";
        return -1;
    }
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";
    hexdump(string("wwHello.txt"));

    return 0;
}

// dump contents of filename to stdout in hex
void hexdump(const string& filename)
{
    fstream ifile(filename.c_str(),
        ios_base::in | ios_base::binary);
    char *ibuff = new char[IBUFSIZE];
    char *obuff = new char[(IBUFSIZE*2)+1];
    int i;

    if(!ifile.is_open())
    {
        cout << "Cannot Open " << filename.c_str()
             << " for reading\n";
        return;
    }
    if(!ibuff || !obuff)
    {
        cout << "Cannot Allocate buffers\n";
        ifile.close();
        return;
    }

    while(!ifile.eof())
    {
        memset(obuff,0,(IBUFSIZE*2)+1);
        memset(ibuff,0,IBUFSIZE);
        ifile.read(ibuff,IBUFSIZE);

        // corner case where file is exactly a multiple of
        // 16 bytes in length
        if(ibuff[0] == 0 && ifile.eof())
            break;

        for(i = 0; i < IBUFSIZE; i++)
        {
            if(ibuff[i] >= ' ')
                obuff[i] = ibuff[i];
            else
                obuff[i] = '.';

            cout << setfill('0') << setw(2) << hex
                 << (int)ibuff[i] << ' ';
        }
        cout << "  " << obuff << endl;
    }
    ifile.close();
}
```

```Output
Hex Dump of wcHello.txt - note that output is ANSI chars:
48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....

Hex Dump of wwHello.txt - note that output is wchar_t chars:
48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o. .W.o.
72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_filebuf](#basic_filebuf)|Konstruiert ein Objekt vom Typ `basic_filebuf`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Verknüpft einen Typnamen mit dem `Elem`-Vorlagenparameter.|
|[int_type](#int_type)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|
|[off_type](#off_type)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|
|[pos_type](#pos_type)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|
|[traits_type](#traits_type)|Verknüpft einen Typnamen mit dem `Tr`-Vorlagenparameter.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[close](#close)|Schließt eine Datei.|
|[is_open](#is_open)|Gibt an, ob eine Datei geöffnet ist.|
|[open](#open)|Öffnet eine Datei.|
|[overflow](#overflow)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|
|[pbackfail](#pbackfail)|Die geschützte virtuelle Memberfunktion versucht, ein Element zurück in den Eingabestream zu versetzen und es dann zum aktuellen Element zu ernennen (wird mit dem nächsten Zeiger darauf gezeigt).|
|[seekoff](#seekoff)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|
|[seekpos](#seekpos)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|
|[setbuf](#setbuf)|Die geschützte virtuelle Memberfunktion führt einen für jeden abgeleiteten Streampuffer bestimmten Vorgang aus.|
|[Swap](#swap)|Tauscht den `basic_filebuf`-Inhalt mit dem Inhalt des angegebenen `basic_filebuf`-Parameters.|
|[sync](#sync)|Die geschützte virtuelle Funktion versucht, die gesteuerten Streams mit zugehörigen externen Streams zu synchronisieren.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Die geschützte virtuelle Funktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.|
|[underflow](#underflow)|Die geschützte virtuelle Funktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.|

## <a name="requirements"></a>Anforderungen

**Header:** \<fstream>

**Namespace:** std

## <a name="basic_filebuf"></a> basic_filebuf::basic_filebuf

Konstruiert ein Objekt vom Typ `basic_filebuf`.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Hinweise

Der erste Konstruktor speichert einen NULL-Zeiger in allen Zeigern, die den Eingabe- und Ausgabepuffer steuern. Außerdem wird ein NULL-Zeiger im Dateizeiger gespeichert.

Der zweite Konstruktor initialisiert das Objekt mit dem Inhalt von `right`, das als rvalue-Verweis behandelt wird.

## <a name="char_type"></a> basic_filebuf::char_type

Verknüpft einen Typnamen mit dem `Elem`-Vorlagenparameter.

```cpp
typedef Elem char_type;
```

## <a name="close"></a> basic_filebuf::close

Schließt eine Datei.

```cpp
basic_filebuf<Elem, Tr> *close();
```

### <a name="return-value"></a>Rückgabewert

Die Memberfunktion gibt einen NULL-Zeiger zurück, wenn der Dateizeiger ein NULL-Zeiger ist.

### <a name="remarks"></a>Hinweise

`close` Aufrufe `fclose`( **fp**). Wenn diese Funktion einen Wert zurückgibt, der ungleich Null ist, gibt die Funktion einen NULL-Zeiger zurück. Andernfalls wird **this** zurückgegeben, um anzugeben, dass die Datei erfolgreich geschlossen wurde.

Bei einem breiten Stream ruft die Funktion [overflow](#overflow) auf, wenn seit der Öffnung des Streams oder des letzten Aufrufs von `streampos` Einfügungen vorgenommen wurden. Es fügt auch eine beliebige Sequenz, die erforderlich sind, um den ursprünglichen konvertierungszustand mithilfe des dateikonvertierungs-Facets wiederherzustellen `fac` aufzurufende `fac.unshift` je nach Bedarf. Jedes Element `byte` des Typs **Char** so erstellt wurde, die durch den Dateizeiger zugeordneten Stream geschrieben `fp` oder durch aufeinander folgende Aufrufe des Formulars `fputc`( **Byte**, **fp**). Wenn der Aufruf von `fac.unshift` oder ein Schreibvorgang fehlschlägt, wird die Funktion nicht erfolgreich ist.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird angenommen, dass sich zwei Dateien im aktuellen Verzeichnis befinden: basic_filebuf_close.txt (der Inhalt ist „testing“) und iotest.txt (der Inhalt ist „ssss“).

```cpp
// basic_filebuf_close.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main() {
   using namespace std;
   ifstream file;
   basic_ifstream <wchar_t> wfile;
   char c;
   // Open and close with a basic_filebuf
   file.rdbuf()->open( "basic_filebuf_close.txt", ios::in );
   file >> c;
   cout << c << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "iotest.txt" );
   file >> c;
   cout << c << endl;
   file.close( );

   // open a file with a wide character name
   wfile.open( L"iotest.txt" );

   // Open and close a nonexistent with a basic_filebuf
   file.rdbuf()->open( "ziotest.txt", ios::in );
   cout << file.fail() << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "ziotest.txt" );
   cout << file.fail() << endl;
   file.close( );
}
```

```Output
t
s
0
1
```

## <a name="int_type"></a> basic_filebuf::int_type

Stellt den Typ im Bereich von Basic_filebuf dem Typ mit dem gleichen Namen in der `Tr` Bereich.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="is_open"></a> basic_filebuf::is_open

Gibt an, ob eine Datei geöffnet ist.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Rückgabewert

**RUE** wenn der Dateizeiger kein NULL-Zeiger ist.

### <a name="example"></a>Beispiel

```cpp
// basic_filebuf_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   cout << boolalpha << file.rdbuf( )->is_open( ) << endl;

   file.open( "basic_filebuf_is_open.cpp" );
   cout << file.rdbuf( )->is_open( ) << endl;
}
```

```Output
false
true
```

## <a name="off_type"></a> basic_filebuf::off_type

Stellt den Typ im Bereich von Basic_filebuf dem Typ mit dem gleichen Namen in der `Tr` Bereich.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="open"></a> basic_filebuf::open

Öffnet eine Datei.

```cpp
basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>Parameter

*_Filename*<br/>
Der Name der zu öffnenden Datei.

*_Modus*<br/>
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Der Standardwert der dateiöffnung, entspricht die *Shflag* Parameter im [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="return-value"></a>Rückgabewert

Wenn der Dateizeiger ein NULL-Zeiger ist, gibt die Funktion einen NULL-Zeiger zurück. Andernfalls wird **this** zurückgegeben.

### <a name="remarks"></a>Hinweise

Die Memberfunktion öffnet die Datei mit dem Dateinamen *Dateiname*, indem sie [fopen](../c-runtime-library/reference/fopen-wfopen.md)( *Dateiname*, **strmode**) aufruft. `strmode` wird von bestimmt **Modus &**~ ( [ate](../standard-library/ios-base-class.md#openmode) & &#124; [binäre](../standard-library/ios-base-class.md#openmode)):

- `ios_base::in` wird **"R"** (vorhandene Datei zum Lesen öffnen).

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) oder **ios_base::out &#124; ios_base::trunc** wird zu **"w"** (vorhandene Datei abschneiden oder zum Schreiben erstellen).

- **ios_base::out &#124; app** wird zu **"a"** (vorhandene Datei zum Anfügen aller Schreibvorgänge öffnen).

- **ios_base::in &#124; ios_base::out** wird zu **"r+"** (vorhandene Datei zum Lesen und Schreiben öffnen).

- **ios_base::in &#124; ios_base::out &#124; ios_base::trunc** wird zu **"w+"** (vorhandene Datei abschneiden oder zum Lesen und Schreiben erstellen).

- **ios_base::in &#124; ios_base::out &#124; ios_base::trunc** wird zu **"a+"** (vorhandene Datei zum Lesen und Anfügen aller Schreibvorgänge öffnen).

Wenn **Mode & ios_base:: Binary** ist ungleich NULL ist, fügt die Funktion an `b` zu `strmode` zu einen binären Stream anstelle eines Textstreams zu öffnen. Es speichert dann den Rückgabewert von `fopen` im Dateizeiger `fp`. Wenn **mode & ios_base::ate** ungleich null ist, und der Dateizeiger kein NULL-Zeiger ist, ruft die Funktion `fseek`( **fp**, 0, `SEEK_END`) auf, um den Stream am Ende der Datei zu positionieren. Wenn es sich bei dieser Positionierung ein Fehler auftritt, ruft die Funktion [schließen](#close)( `fp`) und einen null-Zeiger im Dateizeiger gespeichert.

Wenn der Dateizeiger kein NULL-Zeiger ist, bestimmt die Funktion das Dateikonvertierungs-Facet: `use_facet`< `codecvt`< **Elem**, `char`, **traits_type::**[state_type](../standard-library/char-traits-struct.md#state_type)> >( [getloc](../standard-library/basic-streambuf-class.md#getloc)) für die Verwendung durch [underflow](#underflow) und [overflow](#overflow).

Wenn der Dateizeiger ein NULL-Zeiger ist, gibt die Funktion einen NULL-Zeiger zurück. Andernfalls wird **this** zurückgegeben.

### <a name="example"></a>Beispiel

Sie finden ein Beispiel, in dem `open` verwendet wird, unter [basic_filebuf::close](#close).

## <a name="op_eq"></a> basic_filebuf::operator=

Weist den Inhalt dieses Streampufferobjekts zu. Dies ist eine Verschiebezuweisung über einen rvalue, die keine Kopie hinterlässt.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Ein rvalue-Verweis auf ein [basic_filebuf](../standard-library/basic-filebuf-class.md)-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt *dies zurück.

### <a name="remarks"></a>Hinweise

Der Memberoperator ersetzt den Inhalt des Objekts anhand der Inhalte des *rechten*, als Rvalue-Verweis behandelt. Weitere Informationen finden Sie unter [RValue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="overflow"></a> basic_filebuf::overflow

Wird aufgerufen, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parameter

*_Meta*<br/>
Das Zeichen, das in den Puffer eingefügt oder `traits_type::eof`.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `traits_type::eof` zurückgegeben. Andernfalls wird **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) zurückgegeben.

### <a name="remarks"></a>Hinweise

Wenn *_Meta* **! = Traits_type::**[eof](../standard-library/char-traits-struct.md#eof), die geschützte virtuelle Memberfunktion versucht, das Element eingefügt **ch = Traits_type::** [ To_char_type](../standard-library/char-traits-struct.md#to_char_type)(*_Meta*) in den Ausgabepuffer. Hierfür gibt es verschiedene Möglichkeiten:

- Wenn eine Schreibposition verfügbar ist, kann das Element in der Schreibposition gespeichert werden, und der nächste Zeiger für den Ausgabepuffer kann inkrementiert werden.

- Eine Schreibposition kann verfügbar gemacht werden, indem neuer oder zusätzlicher Speicher für den Ausgabepuffer zugewiesen wird.

- Sie können ausstehende Ausgaben im Ausgabepuffer, gefolgt von konvertieren `ch`, mithilfe des dateikonvertierungs-Facets `fac` Aufrufen `fac.out` je nach Bedarf. Jedes Element `ch` des Typs *Char* so erstellt wurde, die durch den Dateizeiger zugeordneten Stream geschrieben `fp` oder durch aufeinander folgende Aufrufe des Formulars `fputc`( **ch**, **fp**). Wenn bei einer Konvertierung oder einem Schreibvorgang ein Fehler auftritt, kann die Funktion nicht erfolgreich ausgeführt werden.

## <a name="pbackfail"></a> basic_filebuf::pbackfail

Versucht, ein Element zurück in den Eingabestream zu versetzen und es dann zum aktuellen Element zu ernennen (wird mit dem nächsten Zeiger darauf gezeigt).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parameter

*_Meta*<br/>
Das Zeichen, das in den Puffer eingefügt werden soll, oder `traits_type::eof`.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird `traits_type::eof` zurückgegeben. Andernfalls wird **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) zurückgegeben.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versetzt ein Element zurück in den Eingabepuffer und ernennt es dann zum aktuellen Element (wird mit dem nächsten Zeiger darauf gezeigt). Bei _ *Meta* **== traits_type::**[eof](../standard-library/char-traits-struct.md#eof) ist das Element für den Pushback das Element, das sich bereits vor dem aktuellen Element im Stream befindet. Andernfalls wird dieses Element durch **ch = traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) ersetzt. Ein Element kann auf verschiedene Arten durch die Funktion wiederhergestellt werden:

- Wenn eine Position zur Wiederherstellung zur Verfügung steht, und das Element dort gespeicherten gleich `ch`, kann er den nächsten Zeiger für den Eingabepuffer verringert.

- Wenn die Funktion ausführen, kann eine `putback` Position verfügbar ist, kann es zu diesem Zweck, legen Sie den nächsten Zeiger darauf an, die zu positionieren, und speichern `ch` an dieser Position.

- Wenn die Funktion ein Element zurück in den Eingabestream durchführen kann, hierfür, z. B. durch Aufrufen von `ungetc` für ein Element vom Typ **Char**.

## <a name="pos_type"></a> basic_filebuf::pos_type

Stellt den Typ im Bereich von Basic_filebuf dem Typ mit dem gleichen Namen in der `Tr` Bereich.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a> basic_filebuf::seekoff

Versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.

```cpp
virtual pos_type seekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Off*<br/>
Die Position, die für die Suche, relativ zum *_Way*.

*_Way*<br/>
Gibt den Startpunkt für Offsetvorgänge an. Mögliche Werte sind unter [seekdir](../standard-library/ios-base-class.md#seekdir) aufgeführt.

*_Which*<br/>
Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden.

### <a name="return-value"></a>Rückgabewert

Gibt die neue Position oder eine ungültige Streamposition zurück.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern. Für ein Objekt der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> kann eine Streamposition durch ein Objekt vom Typ `fpos_t` dargestellt werden, das ein Offset und Statusinformationen speichert, die notwendig sind, um einen breiten Stream zu analysieren. Das Offset Null legt das erste Element des Streams fest. (Ein Objekt vom Typ [pos_type](../standard-library/basic-streambuf-class.md#pos_type) speichert mindestens ein `fpos_t`-Objekt.)

Bei einer Datei, die sowohl zum Lesen als auch zum Schreiben geöffnet wird, werden sowohl die Eingabe- als auch Ausgabestreams zusammen positioniert. Zum Wechseln zwischen Einfügen und Extrahieren müssen Sie entweder [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) oder [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos) aufrufen. Aufrufe von `pubseekoff` (und somit von `seekoff`) haben verschiedene Einschränkungen für [Textstreams](../c-runtime-library/text-and-binary-streams.md), [binäre Streams](../c-runtime-library/text-and-binary-streams.md) und [breite Streams](../c-runtime-library/byte-and-wide-streams.md).

Wenn der Dateizeiger `fp` ist ein null-Zeiger, schlägt die Funktion. Andernfalls versucht sie, die Streamposition durch Aufruf von `fseek`( **fp**, `_Off`, `_Way`) zu ändern. Die Funktion erfolgreich ausgeführt und die resultierende Position `fposn` kann bestimmt werden, indem `fgetpos`( **fp**, **& Fposn**), die Funktion erfolgreich ist. Wenn die Funktion erfolgreich ist, wird einen Wert vom Typ `pos_type` mit `fposn`. Andernfalls gibt sie eine ungültige Streamposition zurück.

## <a name="seekpos"></a> basic_filebuf::seekpos

Versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Sp*<br/>
Die Position, nach der gesucht werden soll.

*_Which*<br/>
Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden.

### <a name="return-value"></a>Rückgabewert

Wenn der Dateizeiger `fp` ist ein null-Zeiger, schlägt die Funktion. Andernfalls versucht Sie, die die Position im Stream durch Aufrufen von alter `fsetpos`( **fp**, **& Fposn**), wobei `fposn` ist die `fpos_t` in gespeicherten Objekts `pos`. Wenn diese Funktion erfolgreich ausgeführt wurde, gibt die Funktion `pos` zurück. Andernfalls gibt sie eine ungültige Streamposition zurück. Vergleichen Sie den Rückgabewert mit `pos_type(off_type(-1))`, um festzustellen, ob die Streamposition ungültig ist.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern. Für ein Objekt der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**> kann eine Streamposition durch ein Objekt vom Typ `fpos_t` dargestellt werden, das ein Offset und Statusinformationen speichert, die notwendig sind, um einen breiten Stream zu analysieren. Das Offset Null legt das erste Element des Streams fest. (Ein Objekt vom Typ `pos_type` speichert mindestens ein `fpos_t`-Objekt.)

Bei einer Datei, die sowohl zum Lesen als auch zum Schreiben geöffnet wird, werden sowohl die Eingabe- als auch Ausgabestreams zusammen positioniert. Zum Wechseln zwischen Einfügen und Extrahieren müssen Sie entweder [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) oder [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos) aufrufen. Aufrufe von `pubseekoff` (und somit von `seekoff`) haben verschiedene Einschränkungen für Textstreams, binäre Streams und breite Streams.

Bei einem breiten Stream ruft die Funktion [overflow](#overflow) auf, wenn seit der Öffnung des Streams oder des letzten Aufrufs von `streampos` Einfügungen vorgenommen wurden. Es fügt auch eine beliebige Sequenz, die erforderlich sind, um den ursprünglichen konvertierungszustand mithilfe des dateikonvertierungs-Facets wiederherzustellen `fac` aufzurufende **Fac** `.unshift` je nach Bedarf. Jedes Element `byte` des Typs **Char** so erstellt wurde, die durch den Dateizeiger zugeordneten Stream geschrieben `fp` oder durch aufeinander folgende Aufrufe des Formulars `fputc`( **Byte**, **fp**). Wenn der Aufruf von `fac.unshift` oder ein Schreibvorgang fehlschlägt, wird die Funktion nicht erfolgreich ist.

## <a name="setbuf"></a> basic_filebuf::setbuf

Führt einen für jeden abgeleiteten Streampuffer bestimmten Vorgang aus.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parameter

*_Buffer*<br/>
Ein Zeiger auf einen Puffer.

*count*<br/>
Größe des Puffers.

### <a name="return-value"></a>Rückgabewert

Die geschützte Memberfunktion gibt Null zurück, wenn der Dateizeiger `fp` ein NULL-Zeiger ist.

### <a name="remarks"></a>Hinweise

`setbuf` ruft `setvbuf`( **fp**, ( `char` \*) `_Buffer`, `_IOFBF`, `count` \* `sizeof` ( **Elem**) ) ab, um das Array von `count`-Elementen, die bei _ *Buffer* beginnen, als Puffer an den Stream bereitzustellen. Wenn diese Funktion einen Wert zurückgibt, der ungleich Null ist, gibt die Funktion einen NULL-Zeiger zurück. Andernfalls wird **this** zurückgegeben, um den Erfolg zu signalisieren.

## <a name="swap"></a> basic_filebuf::swap

Tauscht den Inhalt dieses `basic_filebuf`-Objekts gegen den Inhalt des bereitgestellten `basic_filebuf`-Objekts aus.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Ein `lvalue`-Verweis auf ein anderes `basic_filebuf`-Objekt.

## <a name="sync"></a> basic_filebuf::sync

Versucht, die gesteuerten Streams mit zugehörigen externen Streams zu synchronisieren.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Rückgabewert

Gibt zurück auf NULL, wenn der Dateizeiger `fp` ist ein null-Zeiger. Andernfalls wird null nur zurückgegeben, wenn Aufrufe von [overflow](#overflow) und `fflush`( **fp**) erfolgreich ausstehende Ausgaben aus dem Stream leeren.

## <a name="traits_type"></a> basic_filebuf::traits_type

Verknüpft einen Typnamen mit dem `Tr`-Vorlagenparameter.

```cpp
typedef Tr traits_type;
```

## <a name="underflow"></a> basic_filebuf::underflow

Extrahiert das aktuelle Element aus dem Eingabestream.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird **traits_type::**[eof](../standard-library/char-traits-struct.md#eof) zurückgegeben. Andernfalls wird `ch`, konvertiert, wie im Abschnitt "Hinweise" beschrieben.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion versucht, das aktuelle Element extrahieren `ch` aus der Eingabe nutzen und Zurückgeben des Elements als **Traits_type::**[To_int_type](../standard-library/char-traits-struct.md#to_int_type)(`ch`). Hierfür gibt es verschiedene Möglichkeiten:

- Wenn eine Leseposition verfügbar ist, dauert es `ch` wie das Element in der Leseposition gespeichert, und den nächsten Zeiger für den Eingabepuffer verschiebt.

- Sie können eine oder mehrere Elemente des Typs gelesen **Char**, wie durch aufeinander folgende Aufrufe des Formulars `fgetc`(**fp**), und wandeln die Dateien auf ein Element **ch** des Typs `Elem`mithilfe der Datei Konvertierung Facet Fac aufzurufende `fac.in` je nach Bedarf. Wenn ein Lesevorgang oder eine Konvertierung fehlschlägt, kann die Funktion nicht erfolgreich ausgeführt werden.

## <a name="see-also"></a>Siehe auch

[\<fstream>](../standard-library/fstream.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
