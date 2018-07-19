---
title: basic_ostream-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- ostream/std::basic_ostream
- ostream/std::basic_ostream::flush
- ostream/std::basic_ostream::put
- ostream/std::basic_ostream::seekp
- ostream/std::basic_ostream::sentry
- ostream/std::basic_ostream::swap
- ostream/std::basic_ostream::tellp
- ostream/std::basic_ostream::write
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ostream [C++]
- std::basic_ostream [C++], flush
- std::basic_ostream [C++], put
- std::basic_ostream [C++], seekp
- std::basic_ostream [C++], sentry
- std::basic_ostream [C++], swap
- std::basic_ostream [C++], tellp
- std::basic_ostream [C++], write
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be74641b229fbf888504df72a97f8a5c025d9b7b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963715"
---
# <a name="basicostream-class"></a>basic_ostream-Klasse

Diese Vorlagenklasse beschreibt ein Objekt, das steuert, Einfügen von Elementen und codierten Objekten in einen Streampuffer mit Elementen des Typs `Elem`, auch bekannt als [Char_type](../standard-library/basic-ios-class.md#char_type), dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`, auch bekannt als [Traits_type](../standard-library/basic-ios-class.md#traits_type).

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Parameter

*Elem* ein `char_type`.

*TR* das Zeichen `traits_type`.

## <a name="remarks"></a>Hinweise

Die meisten der Memberfunktionen, die [operator<<](#op_lt_lt) überladen, sind Funktionen für die formatierte Ausgabe. Sie entsprechen dem folgenden Muster:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
 {try
 {<convert and insert elements
    accumulate flags in state> }
    catch (...)
 {try
 {setstate(badbit);

}
    catch (...)
 {}
    if ((exceptions()& badbit) != 0)
    throw; }}
width(0);
// Except for operator<<(Elem)
setstate(state);

return (*this);
```

Zwei weitere Memberfunktionen sind Funktionen für unformatierte Ausgabe. Sie entsprechen dem folgenden Muster:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (!ok)
    state |= badbit;
else
 {try
 {<obtain and insert elements
    accumulate flags in state> }
    catch (...)
 {try
 {setstate(badbit);

}
    catch (...)
 {}
    if ((exceptions()& badbit) != 0)
    throw; }}
setstate(state);

return (*this);
```

Beide Gruppen von Funktionen rufen [Setstate](../standard-library/basic-ios-class.md#setstate)(**Badbit**) Wenn sie beim Einfügen von Elementen einen Fehler feststellen.

Ein Objekt der Klasse basic_istream \< **Elem**, **Tr**> speichert nur ein virtuelles öffentliches Basisobjekt der Klasse [basic_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr>**.

## <a name="example"></a>Beispiel

Weitere Informationen zu Ausgabestreams finden Sie im Beispiel für die [basic_ofstream-Klasse](../standard-library/basic-ofstream-class.md).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_ostream](#basic_ostream)|Erstellt ein `basic_ostream`-Objekt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[flush](#flush)|Leert den Puffer.|
|[put](#put)|Schreibt ein Zeichen in einen Stream.|
|[seekp](#seekp)|Setzt die Position im Ausgabestream zurück.|
|[sentry](#sentry)|Die geschachtelte Klasse beschreibt ein Objekt, dessen Deklaration die Funktionen für formatierte Ausgabe und für unformatierte Ausgabe strukturiert.|
|[swap](#op_eq)|Tauscht die Werte dieses `basic_ostream`-Objekts gegen die Werte des bereitgestellten `basic_ostream`-Objekts aus.|
|[tellp](#tellp)|Meldet die Position im Ausgabestream.|
|[write](#write)|Schreibt Zeichen in einen Stream.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#basic_ostream_operator_eq)|Weist diesem Objekt den Wert des bereitgestellten `basic_ostream`-Objektparameters zu.|
|[operator<<](#basic_ostream_operator_lt_lt)|Schreibt in den Stream.|

## <a name="requirements"></a>Anforderungen

**Header:** \<ostream>

**Namespace:** std

## <a name="basic_ostream"></a> basic_ostream::basic_ostream

Erstellt ein `basic_ostream`-Objekt.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>Parameter

*Strbuf* ein Objekt des Typs ["basic_streambuf"](../standard-library/basic-streambuf-class.md).

*_Isstd* **"true"** Wenn dies einen Standardstream handelt; andernfalls **"false"**.

*richtige* einen Rvalue-Verweis auf ein Objekt des Typs `basic_ostream`.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisobjekte durch Aufrufen von [init](../standard-library/basic-ios-class.md#init)(`strbuf`). Der zweite Konstruktor initialisiert die Basisklasse durch Aufrufen von [basic_ios::move](../standard-library/basic-ios-class.md#move)`(right)`.

### <a name="example"></a>Beispiel

Weitere Informationen zu Ausgabestreams finden Sie im Beispiel für [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream).

## <a name="flush"></a> basic_ostream::flush

Leert den Puffer.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das basic_ostream-Objekt.

### <a name="remarks"></a>Hinweise

Wenn [rdbuf](../standard-library/basic-ios-class.md#rdbuf) kein NULL-Zeiger ist, ruft die Funktion **rdbuf->**[pubsync](../standard-library/basic-streambuf-class.md#pubsync) auf. Wenn -1 zurückgegeben wird, ruft die Funktion [setstate](../standard-library/basic-ios-class.md#setstate) ( **badbit**) auf. Sie gibt **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "test";
   cout.flush();
}
```

```Output
test
```

## <a name="basic_ostream_operator_lt_lt"></a> basic_ostream::operator&lt;&lt;

Schreibt in den Stream.

```cpp
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

### <a name="parameters"></a>Parameter

*Pfn* einen Funktionszeiger.

*Strbuf* ein Zeiger auf eine `stream_buf` Objekt.

*Val* ein Element, in den Stream geschrieben werden.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das basic_ostream-Objekt.

### <a name="remarks"></a>Hinweise

Die \<Ostream >-Header definiert außerdem mehrere globale Einfügeoperatoren. Weitere Informationen finden Sie unter [Operator <<](../standard-library/ostream-operators.md#op_lt_lt).

Die erste Memberfunktion stellt sicher, dass einen Ausdruck der Form `ostr << endl` Aufrufe [Endl](../standard-library/ostream-functions.md#endl)**(Ostr)**, und gibt dann zurück  **\*dies**. Die zweiten und dritten Funktionen stellen sicher, dass andere Manipulatoren, z.B. [hex](../standard-library/ios-functions.md#hex), sich ähnlich verhalten. Die übrigen Funktionen sind alle formatierte Ausgabefunktionen.

Die Funktion

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

extrahiert Elemente aus *Strbuf*, wenn *Strbuf* ist kein null-Zeiger ist, und fügt sie. Die Extrahierung hält am Ende der Datei an, oder wenn eine Extrahierung eine Ausnahme auslöst (die erneut ausgelöst wird). Sie hält ebenfalls an, ohne das jeweilige Element zu extrahieren, wenn bei einer Einfügung ein Fehler auftritt. Wenn die Funktion kein Element einfügt, oder wenn eine Extahierung eine Ausnahme auslöst, ruft die Funktion [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**) aus. In jedem Fall gibt die Funktion **\*this** zurück.

Die Funktion

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

Konvertiert `_Val` in ein boolesches Feld und fügt es durch Aufrufen von [Use_facet](../standard-library/basic-filebuf-class.md#open)**< Num_put\<Elem, OutIt >**`(`[Getloc](../standard-library/ios-base-class.md#getloc)). [put](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)), **\*this**, `getloc`, **val**). Hier `OutIt` ist definiert als [Ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Elem, Tr >**. Die Funktion gibt **\*this** zurück.

Die Funktionen

```cpp
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

Konvertieren *Val* in ein numerisches Feld und fügen Sie es durch Aufrufen von **Use_facet < Num_put\<Elem, OutIt >**(`getloc`). **put**(**OutIt**(`rdbuf`), **\*this**, `getloc`, **val**). Hier ist **OutIt** als **ostreambuf_iterator\<Elem, Tr>** definiert. Die Funktion gibt **\*this** zurück.

Die Funktionen

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

Konvertieren *Val* in ein numerisches Feld und fügen Sie es durch Aufrufen von **Use_facet < Num_put\<Elem, OutIt >**(`getloc`)**. put**(**OutIt**(`rdbuf`),  **\*dies**, `getloc`, **Val**). Hier ist **OutIt** als **ostreambuf_iterator\<Elem, Tr>** definiert. Die Funktion gibt **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_ostream_op_write.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```

## <a name="op_eq"></a> basic_ostream::operator=

Weist diesem Objekt Werte für den bereitgestellten `basic_ostream`-Objektparameter zu.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Parameter

*richtige* ein `rvalue` Verweis auf eine `basic_ostream` Objekt.

### <a name="remarks"></a>Hinweise

Der Memberoperator ruft swap `(right)` auf.

## <a name="put"></a> basic_ostream::put

Schreibt ein Zeichen in einen Stream.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>Parameter

*_Ch* ein Zeichen.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das basic_ostream-Objekt.

### <a name="remarks"></a>Hinweise

Die unformatierte Ausgabefunktion fügt das Element *_Ch*. Sie gibt **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_ostream_put.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout.put( 'v' );
   cout << endl;
   wcout.put( L'l' );
}
```

```Output
v
l
```

## <a name="seekp"></a> basic_ostream::seekp

Setzt die Position im Ausgabestream zurück.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Parameter

*_Pos* die Position im Stream.

*_Off* das Offset relativ zu *_Way*.

*_Way* eines der [ios_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Enumerationen.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das basic_ostream-Objekt.

### <a name="remarks"></a>Hinweise

Wenn [fehlschlagen](../standard-library/basic-ios-class.md#fail) ist **"false"**, ruft die erste Memberfunktion **Newpos =** [Rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [Pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos*), für einige `pos_type` temporäres Objekt `newpos`. Wenn `fail` ist "false", die zweite Funktion ruft **Newpos = rdbuf->** [Pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(*_Off, _Way*). In jedem Fall ruft die Funktion **istr.**[setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**) auf, wenn (`off_type`)**newpos ==** (`off_type`)(-1)(-1) (die Positionierung schlägt fehl). Beide Funktionen geben **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_ostream_seekp.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main()
{
    using namespace std;
    ofstream x("basic_ostream_seekp.txt");
    streamoff i = x.tellp();
    cout << i << endl;
    x << "testing";
    i = x.tellp();
    cout << i << endl;
    x.seekp(2);   // Put char in third char position in file
    x << " ";

    x.seekp(2, ios::end);   // Put char two after end of file
    x << "z";
}
```

```Output
0
7
```

## <a name="sentry"></a> basic_ostream::sentry

Die geschachtelte Klasse beschreibt ein Objekt, dessen Deklaration die Funktionen für formatierte Ausgabe und für unformatierte Ausgabe strukturiert.

Klasse Sentry {public: explizite Sentry (Basic_ostream\<Elem, Tr > & _Ostr); Operator bool() const; ~ sentry();};

### <a name="remarks"></a>Hinweise

Die geschachtelte Klasse beschreibt ein Objekt, dessen Deklaration die Funktionen für formatierte Ausgabe und für unformatierte Ausgabe strukturiert. Wenn **ostr.**[good](../standard-library/basic-ios-class.md#good) **TRUE** ist, und **ostr.**[tie](../standard-library/basic-ios-class.md#tie) kein NULL-Zeiger ist, ruft der Konstruktor **ostr.tie->**[flush](#flush) auf. Der Konstruktor speichert dann den Rückgabewert von `ostr.good` in `status`. Ein späterer Aufruf von `operator bool` liefert diesen gespeicherten Wert.

Wenn `uncaught_exception` **FALSE** zurückgibt, und [flags](../standard-library/ios-base-class.md#flags)**&** [unitbuf](../standard-library/ios-functions.md#unitbuf) ungleich null ist, ruft der Destruktor [flush](#flush) auf.

## <a name="swap"></a> basic_ostream::swap

Tauscht die Werte dieses `basic_ostream`-Objekts gegen die Werte des bereitgestellten `basic_ostream`-Objekts aus.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Parameter

*richtige* einen Verweis auf eine `basic_ostream` Objekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [basic_ios:: Swap](../standard-library/basic-ios-class.md#swap) `(right)` zum Austauschen von den Inhalt dieses Objekts für den Inhalt des *rechten*.

## <a name="tellp"></a> basic_ostream::tellp

Meldet die Position im Ausgabestream.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Rückgabewert

Position im Ausgabestream.

### <a name="remarks"></a>Hinweise

Wenn [fail](../standard-library/basic-ios-class.md#fail) **FALSE** ist, gibt die Memberfunktion [rdbuf](../standard-library/basic-ios-class.md#rdbuf)**->**[pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) (0, `cur`, **in**) zurück. Andernfalls wird `pos_type`(-1) zurückgegeben.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `tellp` finden Sie unter [seekp](#seekp).

## <a name="write"></a> basic_ostream::write

Schreibt Zeichen in einen Stream.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Parameter

*Anzahl* Anzahl von Zeichen in den Stream zu versetzen.

*Str* Zeichen in den Stream zu versetzen.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das basic_ostream-Objekt.

### <a name="remarks"></a>Hinweise

Die [nicht formatierte Ausgabefunktion](../standard-library/basic-ostream-class.md) fügt die Sequenz von *Anzahl* Elemente, die beginnend bei *str*.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `write` finden Sie unter [streamsize](../standard-library/ios-typedefs.md#streamsize).

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
