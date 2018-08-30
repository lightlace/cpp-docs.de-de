---
title: basic_istream-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- istream/std::basic_istream
- istream/std::basic_istream::gcount
- istream/std::basic_istream::get
- istream/std::basic_istream::getline
- 'istream/std::basic_istream::'
- istream/std::basic_istream::peek
- istream/std::basic_istream::putback
- istream/std::basic_istream::read
- istream/std::basic_istream::readsome
- istream/std::basic_istream::seekg
- istream/std::basic_istream::sentry
- istream/std::basic_istream::swap
- istream/std::basic_istream::sync
- istream/std::basic_istream::tellg
- istream/std::basic_istream::unget
dev_langs:
- C++
helpviewer_keywords:
- std::basic_istream [C++]
- std::basic_istream [C++], gcount
- std::basic_istream [C++], get
- std::basic_istream [C++], getline
- std::basic_istream [C++], OVERWRITE
- std::basic_istream [C++], peek
- std::basic_istream [C++], putback
- std::basic_istream [C++], read
- std::basic_istream [C++], readsome
- std::basic_istream [C++], seekg
- std::basic_istream [C++], sentry
- std::basic_istream [C++], swap
- std::basic_istream [C++], sync
- std::basic_istream [C++], tellg
- std::basic_istream [C++], unget
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4250a2b13740b5aa71ca10300a90560ed615f68e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200027"
---
# <a name="basicistream-class"></a>basic_istream-Klasse

Beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer mit Elementen des Typs `Elem` steuert, der auch als [char_type](../standard-library/basic-ios-class.md#char_type) bekannt ist, und dessen Zeichenmerkmale durch die Klasse *Tr* bestimmt werden, die auch als [traits_type](../standard-library/basic-ios-class.md#traits_type) bekannt ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_istream : virtual public basic_ios<Elem, Tr>
```

## <a name="remarks"></a>Hinweise

Die meisten der Memberfunktionen, die [operator>>](#op_gt_gt) überladen, sind Funktionen für die formatierte Eingabe. Sie entsprechen dem folgenden Muster:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```

Viele weitere Memberfunktionen sind Funktionen für unformatierte Eingabe. Sie entsprechen dem folgenden Muster:

```cpp
iostate state = goodbit;
count = 0;    // the value returned by gcount
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```

Beide Gruppen von Funktionen rufen [Setstate](../standard-library/basic-ios-class.md#setstate)(`eofbit`) Wenn sie beim Extrahieren von Elementen den Dateiende feststellen.

Ein Objekt der Klasse `basic_istream`< `Elem`, *Tr*> speichert Folgendes:

- Ein virtuelles öffentliches Basisobjekt der Klasse [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, *Tr*> `.`.

- Eine extraktionsanzahl für den letzten Vorgang unformatierter Eingabe (namens `count` im vorherigen Code).

## <a name="example"></a>Beispiel

Weitere Informationen zu Eingabestreams finden Sie im Beispiel für die [basic_ifstream-Klasse](../standard-library/basic-ifstream-class.md).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_istream](#basic_istream)|Konstruiert ein Objekt vom Typ `basic_istream`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[gcount](#gcount)|Gibt die Anzahl von Zeichen zurück, die bei der letzten unformatierten Eingabe gelesen wurden.|
|[get](#get)|Liest mindestens ein Zeichen aus dem Eingabestream.|
|[getline](#getline)|Liest eine Zeile aus dem Eingabestream.|
|[ignore](#ignore)|Bewirkt, dass eine Anzahl von Elementen ab der aktuellen Leseposition übersprungen werden.|
|[peek](#peek)|Gibt das nächste zu lesende Zeichen zurück.|
|[putback](#putback)|Schreibt ein angegebenes Zeichen in den Stream.|
|[read](#read)|Liest eine angegebene Anzahl von Zeichen aus dem Stream und speichert diese in einem Array.|
|[readsome](#readsome)|Liest nur aus dem Puffer.|
|[seekg](#seekg)|Verschiebt die Leseposition in einem Stream.|
|[sentry](#sentry)|Die geschachtelte Klasse beschreibt ein Objekt, dessen Deklaration die Funktionen für formatierte Eingabe und für unformatierte Eingabe strukturiert.|
|[swap](#swap)|Tauscht dieses `basic_istream`-Objekt gegen den bereitgestellten `basic_istream`-Objektparameter aus.|
|[sync](#sync)|Synchronisiert das Eingabegerät, das dem Stream zugeordnet ist, mit dem Puffer des Streams.|
|[tellg](#tellg)|Meldet die aktuelle Leseposition im Stream.|
|[unget](#unget)|Schreibt das zuletzt gelesene Zeichen zurück in den Stream.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator>>](#op_gt_gt)|Ruft eine Funktion für den Eingabestream auf oder liest formatierte Daten aus dem Eingabestream.|
|[operator=](#op_eq)|Weist den `basic_istream` auf der rechten Seite des Operators diesem Objekt zu. Dies ist eine Verschiebezuweisung mit einem `rvalue`-Verweis, der keine Kopie hinterlässt.|

## <a name="requirements"></a>Anforderungen

**Header:** \<istream>

**Namespace:** std

## <a name="basic_istream"></a> basic_istream::basic_istream

Konstruiert ein Objekt vom Typ `basic_istream`.

```cpp
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>Parameter

*Strbuf* ein Objekt des Typs ["basic_streambuf"](../standard-library/basic-streambuf-class.md).

*_Isstd* **"true"** Wenn dies einen Standardstream handelt; andernfalls **"false"**.

*richtige* ein `basic_istream` zu kopierende Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisobjekte durch Aufrufen von [init](../standard-library/basic-ios-class.md#init)(_S `trbuf`). Außerdem wird null in der Extraktionsanzahl gespeichert. Weitere Informationen zu dieser Extrationsanzahl finden Sie im Bereich „Hinweise“ des Übersichtsthemas [basic_istream-Klasse](../standard-library/basic-istream-class.md).

Der zweite Konstruktor initialisiert die Basisklasse durch Aufrufen von `move( right)`. Es wird auch _R `ight.gcount()` in der Extraktionsanzahl und null in der Extraktionsanzahl für _R `ight` gespeichert.

### <a name="example"></a>Beispiel

Weitere Informationen zu Eingabestreams finden Sie im Beispiel für [basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream).

## <a name="gcount"></a> basic_istream::gcount

Gibt die Anzahl von Zeichen zurück, die bei der letzten unformatierten Eingabe gelesen wurden.

```cpp
streamsize gcount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Extraktionsanzahl.

### <a name="remarks"></a>Hinweise

Verwenden Sie [basic_istream::get](#get), um nicht formatierte Zeichen zu lesen.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_gcount.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   cout << "Type the letter 'a': ";

   ws( cin );
   char c[10];

   cin.get( &c[0],9 );
   cout << c << endl;

   cout << cin.gcount( ) << endl;
}
```

```Output

a

```

```Output

      aType the letter 'a':
a
1
```

## <a name="get"></a> basic_istream::get

Liest mindestens ein Zeichen aus dem Eingabestream.

```cpp
int_type get();

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```

### <a name="parameters"></a>Parameter

*Anzahl* die Anzahl der zu lesenden Zeichen aus `strbuf`.

*Delim* das Zeichen, das den Lesevorgang beenden soll, wenn es vor erreicht wird *Anzahl*.

*Str* eine Zeichenfolge in die geschrieben.

*CH* ein Zeichen, das abgerufen.

*Strbuf* einen Puffer, in die geschrieben.

### <a name="return-value"></a>Rückgabewert

Die parameterlose Form von „get“ gibt das gelesene Element als ganze Zahl oder Ende der Datei zurück. Die übrigen Formen geben den Stream (* `this`) zurück.

### <a name="remarks"></a>Hinweise

Die erste dieser nicht formatierten Eingabefunktionen extrahiert falls möglich ein Element, als wäre `rdbuf`-> `sbumpc` zurückgegeben worden. Andernfalls wird **traits_type::**[eof](../standard-library/char-traits-struct.md#eof) zurückgegeben. Wenn die Funktion kein Element extrahiert, ruft es [Setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`).

Die zweite Funktion extrahiert das [int_type](../standard-library/basic-ios-class.md#int_type)-Element `meta` auf die gleiche Weise. Wenn `meta` mit **traits_type::eof** übereinstimmt, ruft die Funktion `setstate`( **failbit**) auf. Andernfalls wird **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)( `meta`) in `Ch` gespeichert. Die Funktion gibt **\*this** zurück.

Die dritte Funktion gibt **get**(_ *Str*, `count`, `widen`('\ **n**')) zurück.

Die vierte Funktion extrahiert bis zu *Anzahl* - 1 Elemente und speichert sie in das Array, beginnend bei _ *Str*. Sie speichert `char_type` immer nach den extrahierten Elementen, die sie speichert. In der Reihenfolge der Tests hält die Extrahierung hier an:

- Am Ende der Datei.

- Nachdem die Funktion ein Element extrahiert, die gleich vergleicht *Delim*, in diesem Fall das Element wieder an die gesteuerte Sequenz eingefügt wird.

- Nachdem die Funktion extrahiert *Anzahl* - 1 Elemente.

Wenn die Funktion keine Elemente extrahiert, ruft sie `setstate`( **failbit**) auf. In jedem Fall gibt sie **\*this** zurück.

Die fünfte Funktion gibt **get**( **trbuf**, `widen`('\ **n**')) zurück.

Die sechste Funktion extrahiert Elemente und fügt sie in `strbuf`. Die Extrahierung hält am Ende der Datei oder bei einem Element an, das *Delim* entspricht, das nicht extrahiert wird. Sie hält ebenfalls an, ohne die jeweiligen Elemente zu extrahieren, wenn bei einer Einfügung ein Fehler auftritt, oder löst eine Ausnahme aus (die aufgefangen, aber nicht erneut ausgelöst wird). Wenn die Funktion keine Elemente extrahiert, ruft sie `setstate`( **failbit**) auf. In jedem Fall gibt die Funktion **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_get.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   c[0] = cin.get( );
   cin.get( c[1] );
   cin.get( &c[2],3 );
   cin.get( &c[4], 4, '7' );

   cout << c << endl;
}
```

```Output

1111
```

## <a name="getline"></a> basic_istream::getline

Ruft eine Zeile aus dem Eingabestream ab.

```cpp
basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count,
    char_type Delim);
```

### <a name="parameters"></a>Parameter

*Anzahl* die Anzahl der zu lesenden Zeichen aus `strbuf`.

*Delim* das Zeichen, das den Lesevorgang beenden soll, wenn es vor erreicht wird *Anzahl*.

*Str* eine Zeichenfolge in die geschrieben.

### <a name="return-value"></a>Rückgabewert

Der Stream ( **\*this**).

### <a name="remarks"></a>Hinweise

Die erste dieser nicht formatierten Eingabefunktionen gibt **getline**(_ *Str*, `count`, `widen`(' `\`**n**')) zurück.

Die zweite Funktion extrahiert bis zu *Anzahl* - 1 Elemente und speichert sie in das Array, beginnend bei _ *Str*. Das Abschlusszeichen der Zeichenfolge wird immer nach jedem Element gespeichert, das sie speichert. In der Reihenfolge der Tests hält die Extrahierung hier an:

- Am Ende der Datei.

- Nachdem die Funktion ein Element extrahiert, die gleich vergleicht *Delim*, in diesem Fall das Element ist weder zurückgestellt noch an die gesteuerte Sequenz angefügt.

- Nachdem die Funktion extrahiert *Anzahl* - 1 Elemente.

Wenn die Funktion keine Elemente extrahiert oder *Anzahl* - 1 Elemente ruft [Setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). In jedem Fall gibt sie **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_getline.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   cin.getline( &c[0], 5, '2' );
   cout << c << endl;
}
```

```Output

121
```

## <a name="ignore"></a> basic_istream::ignore

Bewirkt, dass eine Anzahl von Elementen ab der aktuellen Leseposition übersprungen werden.

```cpp
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,
    int_type Delim = traits_type::eof());
```

### <a name="parameters"></a>Parameter

*Anzahl* die Anzahl von Elementen, überspringen Sie aus der aktuellen Leseposition.

*Delim* das Element, das bewirkt, wenn vor dem Zieleintrag, aufgetreten dass `ignore` zurückgegeben und zulassen, dass alle Elemente nach *Delim* gelesen werden.

### <a name="return-value"></a>Rückgabewert

Der Stream ( **\*this**).

### <a name="remarks"></a>Hinweise

Die unformatierte Eingabefunktion extrahiert bis zu *Anzahl* Elemente und verwirft sie. Wenn *Anzahl* gleich **Numeric_limits\<Int >:: max**, allerdings wird sie als beliebig groß angesehen. Extrahierung hält früh am Ende der Datei oder für ein Element `Ch` so, dass **Traits_type::**[To_int_type](../standard-library/char-traits-struct.md#to_int_type)( `Ch`) übereinstimmt *Delim* (die Außerdem extrahiert werden). Die Funktion gibt **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_ignore.cpp
// compile with: /EHsc
#include <iostream>
int main( )
{
   using namespace std;
   char chararray[10];
   cout << "Type 'abcdef': ";
   cin.ignore( 5, 'c' );
   cin >> chararray;
   cout << chararray;
}
```

```Output
Type 'abcdef': abcdef
def
```

## <a name="op_gt_gt"></a>  grundlegende\_istream::operator >>

Ruft eine Funktion für den Eingabestream auf oder liest formatierte Daten aus dem Eingabestream.

```cpp
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));
basic_istream& operator>>(basic_streambuf<Elem, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

### <a name="parameters"></a>Parameter

*Pfn* einen Funktionszeiger.

*Strbuf* ein Objekt des Typs `stream_buf`.

*Val* der Wert, der aus dem Stream gelesen.

### <a name="return-value"></a>Rückgabewert

Der Stream ( **\*this**).

### <a name="remarks"></a>Hinweise

Die \<Istream >-Header definiert außerdem mehrere globale Extraktionsoperatoren. Weitere Informationen finden Sie unter [operator>> (\<istream>)](../standard-library/istream-operators.md#op_gt_gt).

Die erste Memberfunktion stellt sicher, dass ein Ausdruck der Form **istr** >> `ws` [ws](../standard-library/istream-functions.md#ws)( **istr**) aufruft, und anschließend **\*this** zurückgibt. Die zweiten und dritten Funktionen stellen sicher, dass andere Manipulatoren, z.B. [hex](../standard-library/ios-functions.md#hex) sich ähnlich verhalten. Die übrigen Funktionen bilden die formatierten Eingabefunktionen.

Die Funktion:

```cpp
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```

extrahiert Elemente, wenn _ *Strbuf* ist kein null-Zeiger ist, und fügt sie in *Strbuf*. Die Extrahierung hält am Ende der Datei an. Sie hält ebenfalls an, ohne die jeweiligen Elemente zu extrahieren, wenn eine Einfügung fehlschlägt, oder löst eine Ausnahme aus (die aufgefangen, aber nicht erneut ausgelöst wird). Wenn die Funktion keine Elemente extrahiert, ruft es [Setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). In jedem Fall gibt die Funktion **\*this** zurück.

Die Funktion:

```cpp
basic_istream& operator>>(bool& val);
```

extrahiert ein Feld und konvertiert es durch Aufrufen von [use_facet](../standard-library/basic-filebuf-class.md#open) < `num_get`\< **Elem**, **InIt**>( [getloc](../standard-library/ios-base-class.md#getloc)) in einen booleschen Wert. [get](../standard-library/ios-base-class.md#getloc)( **InIt**( [rdbuf](../standard-library/basic-ios-class.md#rdbuf)), `Init`(0), **\*this**, `getloc`, `val`). Hier ist **InIt** als [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)\< **Elem**, **Tr**> definiert. Die Funktion gibt **\*this** zurück.

Die Funktionen:

```cpp
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
```

extrahieren alle ein Feld, und konvertieren es durch Aufrufen von `use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`) in einen numerischen Wert. [get](#get)( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, `val`). Hier **InIt** ist definiert als `istreambuf_iterator` \< **Elem**, **Tr**>, und `val` weist den Typ **lange**, **unsigned long**, oder **"void"** <strong>\*</strong> je nach Bedarf.

Wenn der konvertierte Wert kann, mit dem Typ der dargestellt werden `val`, ruft die Funktion [Setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). In jedem Fall gibt die Funktion **\*this** zurück.

Die Funktionen:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

extrahieren alle ein Feld, und konvertieren es durch Aufrufen von `use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`) in einen numerischen Wert. **get**( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, `val`). Hier `InIt` ist definiert als `istreambuf_iterator` \< **Elem**, **Tr**>, und `val` weist den Typ **doppelte** oder **lange doppelte** je nach Bedarf.

Wenn der konvertierte Wert nicht als Typ `val` dargestellt werden kann, ruft die Funktion `setstate`( **failbit**) auf. In jedem Fall gibt sie **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// istream_basic_istream_op_is.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)
{
   if ( i == cin )
   {
      cerr << "i is cin" << endl;
   }
   return i;
}

int main( )
{
   int i = 0;
   cin >> somefunc;
   cin >> i;
   cout << i << endl;
   cin >> hex2;
   cin >> i;
   cout << i << endl;
}
```

## <a name="op_eq"></a> basic_istream::operator=

Weist den `basic_istream` auf der rechten Seite des Operators diesem Objekt zu. Dies ist eine Verschiebezuweisung mit einem `rvalue`-Verweis, der keine Kopie hinterlässt.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>Parameter

*richtige* ein `rvalue` Verweis auf eine `basic_ifstream` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt *dies zurück.

### <a name="remarks"></a>Hinweise

Der Memberoperator ruft swap `( right)` auf.

## <a name="peek"></a> basic_istream::peek

Gibt das nächste zu lesende Zeichen zurück.

```cpp
int_type peek();
```

### <a name="return-value"></a>Rückgabewert

Das nächste zu lesende Zeichen.

### <a name="remarks"></a>Hinweise

Die nicht formatierte Eingabefunktion extrahiert falls möglich ein Element, als wäre `rdbuf` -> [sgetc](../standard-library/basic-streambuf-class.md#sgetc) zurückgegeben worden. Andernfalls wird **traits_type::**[eof](../standard-library/char-traits-struct.md#eof) zurückgegeben.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_peek.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;
   cout << "Type 'abcde': ";

   c2 = cin.peek( );
   cin.getline( &c[0], 9 );

   cout << c2 << " " << c << endl;
}
```

```Output

abcde

```

```Output

      abcdeType 'abcde': abcde
a abcde
```

## <a name="putback"></a> basic_istream::putback

Schreibt ein angegebenes Zeichen in den Stream.

```cpp
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>Parameter

*CH* ein Zeichen zurück in den Stream zu versetzen.

### <a name="return-value"></a>Rückgabewert

Der Stream ( **\*this**).

### <a name="remarks"></a>Hinweise

Die [nicht formatierte Eingabefunktion](../standard-library/basic-istream-class.md) setzt zurück *Ch*, sofern möglich, als wäre [Rdbuf](../standard-library/basic-ios-class.md#rdbuf)`->`[Sputbackc](../standard-library/basic-streambuf-class.md#sputbackc). Wenn Rdbuf null-Zeiger ist oder wenn der Aufruf von `sputbackc` gibt **Traits_type::**[eof](../standard-library/char-traits-struct.md#eof), ruft die Funktion [Setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`). In jedem Fall gibt sie **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_putback.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2, c3;

   c2 = cin.get( );
   c3 = cin.get( );
   cin.putback( c2 );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Output

qwq
```

## <a name="read"></a> basic_istream::read

Liest eine angegebene Anzahl von Zeichen aus dem Stream und speichert diese in einem Array.

Diese Methode ist potenziell unsicher, da sie darauf basiert, dass der Aufrufer überprüft, ob die übergebenen Werte korrekt sind.

```cpp
basic_istream<Elem, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parameter

*Str* Arrays, in dem die Zeichen gelesen.

*Anzahl* die Anzahl der zu lesenden Zeichen.

### <a name="return-value"></a>Rückgabewert

Der Stream ( `*this`).

### <a name="remarks"></a>Hinweise

Die unformatierte Eingabefunktion extrahiert bis zu *Anzahl* Elemente und speichert sie in das Array, beginnend bei _ `Str`. Extrahierung hält früh am Ende der Datei, in dem Fall wird die Funktion ruft [Setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). In jedem Fall gibt sie `*this` zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_read.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
    char c[10];
    int count = 5;

    cout << "Type 'abcde': ";

    // Note: cin::read is potentially unsafe, consider
    // using cin::_Read_s instead.
    cin.read(&c[0], count);
    c[count] = 0;

    cout << c << endl;
}
```

```Output

abcde

```

```Output

      abcdeType 'abcde': abcde
abcde
```

## <a name="readsome"></a> basic_istream::readsome

Liest die angegebene Anzahl von Zeichenwerten.

Diese Methode ist potenziell unsicher, da sie darauf basiert, dass der Aufrufer überprüft, ob die übergebenen Werte korrekt sind.

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parameter

*Str* Arrays, in dem `readsome` die gelesenen Zeichen speichert.

*Anzahl* die Anzahl der zu lesenden Zeichen.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der tatsächlich gelesenen Zeichen, [gcount](#gcount).

### <a name="remarks"></a>Hinweise

Diese nicht formatierte Eingabefunktion extrahiert bis zu *Anzahl* Elemente aus der Eingabe zu streamen, und speichert sie in das Array *str*.

Diese Funktion wartet nicht auf Eingabe. Sie liest alle verfügbaren Daten.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_readsome.cpp
// compile with: /EHsc /W3
#include <iostream>
using namespace std;

int main( )
{
   char c[10];
   int count = 5;

   cout << "Type 'abcdefgh': ";

   // cin.read blocks until user types input.
   // Note: cin::read is potentially unsafe, consider
   // using cin::_Read_s instead.
   cin.read(&c[0], 2);

   // Note: cin::readsome is potentially unsafe, consider
   // using cin::_Readsome_s instead.
   int n = cin.readsome(&c[0], count);  // C4996
   c[n] = 0;
   cout << n << " characters read" << endl;
   cout << c << endl;
}
```

## <a name="seekg"></a> basic_istream::seekg

Verschiebt die Leseposition in einem Stream.

```cpp
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>Parameter

*POS* die absolute Position in die der Lesezeiger verschoben.

*Off* einen Offset zum Verschieben des lesezeigers relativ zum *Weise*.

*Möglichkeit* eines der [ios_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Enumerationen.

### <a name="return-value"></a>Rückgabewert

Der Stream ( **\*this**).

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion führt eine absolute, die zweite Memberfunktion eine relative Suche durch.

> [!NOTE]
> Verwenden Sie die zweite Memberfunktion nicht mit Textdateien, da Standard C++ keine relativen Suchen in Textdateien unterstützt.

Wenn [fehlschlagen](../standard-library/basic-ios-class.md#fail) "false" ist die erste Memberfunktion ruft **Newpos** = [Rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [Pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)( `pos`), für einige `pos_type` temporäres Objekt `newpos`. Wenn `fail` ist "false", die zweite Funktion ruft **Newpos** = **Rdbuf** -> [Pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)( `off`, `way`). In beiden Fällen Wenn ( `off_type`) **Newpos** == ( `off_type`)(-1) (die Positionierung schlägt fehl), ruft die Funktion `istr`. [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`). Beide Funktionen geben **\*this** zurück.

Wenn [fail](../standard-library/basic-ios-class.md#fail) TRUE ist, führen die Memberfunktionen keine Aufgaben durch.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_seekg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
   using namespace std;
   ifstream file;
   char c, c1;

   file.open( "basic_istream_seekg.txt" );
   file.seekg(2);   // seek to position 2
   file >> c;
   cout << c << endl;
}
```

## <a name="sentry"></a> basic_istream::sentry

Die geschachtelte Klasse beschreibt ein Objekt, dessen Deklaration die formatierte und unformatierte Eingabe strukturiert.

Klasse Sentry {public: explizite Sentry (Basic_istream\<Elem, Tr > & _Istr, "bool" _Noskip = False), Operator bool() const;};

### <a name="remarks"></a>Hinweise

Wenn `_Istr.`[good](../standard-library/basic-ios-class.md#good) TRUE ist, führt der Konstruktor Folgendes aus:

- Ruft `_Istr`. [tie](../standard-library/basic-ios-class.md#tie) -> [flush](../standard-library/basic-ostream-class.md#flush) auf, wenn `_Istr`. `tie` kein NULL-Zeiger ist.

- Ruft effektiv [ws](../standard-library/istream-functions.md#ws)( `_Istr`) auf, wenn `_Istr`. [flags](../standard-library/ios-base-class.md#flags)**&**[skipws](../standard-library/ios-functions.md#skipws) ungleich null ist.

Wenn nach Vorbereitungen dieser Art `_Istr`. `good` false ist, ruft der Konstruktor `_Istr`. [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`). Der Konstruktor speichert in jedem Fall den Wert, der von `_Istr`. `good` in `status`. Ein späterer Aufruf von `operator bool` liefert diesen gespeicherten Wert.

## <a name="swap"></a> basic_istream::swap

Tauscht den Inhalt von zwei `basic_istream`-Objekten aus.

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>Parameter

*richtige* ein Lvalue-Verweis auf eine `basic_istream` Objekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [basic_ios::swap](../standard-library/basic-ios-class.md#swap)`(right)` auf. Sie tauscht außerdem die extraktionsanzahl mit der extraktionsanzahl für *rechten*.

## <a name="sync"></a> basic_istream::sync

Synchronisiert das Eingabegerät, das dem Stream zugeordnet ist, mit dem Puffer des Streams.

```cpp
int sync();
```

### <a name="return-value"></a>Rückgabewert

Wenn [rdbuf](../standard-library/basic-ios-class.md#rdbuf) ein NULL-Zeiger ist, gibt die Funktion -1 zurück. Andernfalls ruft sie `rdbuf` -> [pubsync](../standard-library/basic-streambuf-class.md#pubsync) auf. Wenn-1 zurückgegeben wird, ruft die Funktion [Setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`) und gibt-1 zurück. Andernfalls wird von der Funktion null zurückgegeben.

## <a name="tellg"></a> basic_istream::tellg

Meldet die aktuelle Leseposition im Stream.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Position in dem Stream.

### <a name="remarks"></a>Hinweise

Wenn [fail](../standard-library/basic-ios-class.md#fail) FALSE ist, gibt die Memberfunktion [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) (0, `cur`**in**) zurück. Andernfalls wird `pos_type`(-1) zurückgegeben.

### <a name="example"></a>Beispiel

```cpp
// basic_istream_tellg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;
    ifstream file;
    char c;
    streamoff i;

    file.open("basic_istream_tellg.txt");
    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;

    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;
}
```

## <a name="unget"></a> basic_istream::unget

Schreibt das zuletzt gelesene Zeichen zurück in den Stream.

```cpp
basic_istream<Elem, Tr>& unget();
```

### <a name="return-value"></a>Rückgabewert

Der Stream ( **\*this**).

### <a name="remarks"></a>Hinweise

Die [nicht formatierte Eingabefunktion](../standard-library/basic-istream-class.md) stellt, wenn möglich, das vorherige Element im Stream wieder her, als wäre `rdbuf` -> [sungetc](../standard-library/basic-streambuf-class.md#sungetc) aufgerufen worden. Wenn [Rdbuf](../standard-library/basic-ios-class.md#rdbuf) ein null-Zeiger ist oder wenn der Aufruf von `sungetc` gibt **Traits_type::**[eof](../standard-library/basic-ios-class.md#eof), ruft die Funktion [Setstate](../standard-library/basic-ios-class.md#setstate)( `badbit`). In jedem Fall gibt sie **\*this** zurück.

Informationen dazu, wann bei `unget` ein Fehler auftreten könnte, finden Sie unter [basic_streambuf::sungetc](../standard-library/basic-streambuf-class.md#sungetc).

### <a name="example"></a>Beispiel

```cpp
// basic_istream_unget.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;

   cout << "Type 'abc': ";
   c2 = cin.get( );
   cin.unget( );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Output

abc

```

```Output

      abcType 'abc': abc
abc
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
