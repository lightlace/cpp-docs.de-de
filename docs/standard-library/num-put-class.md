---
title: num_put-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocnum/std::num_put
- locale/std::num_put::char_type
- locale/std::num_put::iter_type
- locale/std::num_put::do_put
- locale/std::num_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::num_put [C++]
- std::num_put [C++], char_type
- std::num_put [C++], iter_type
- std::num_put [C++], do_put
- std::num_put [C++], put
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a860f7c266685e7e10f9b4cbe46c280c356f2681
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862035"
---
# <a name="numput-class"></a>num_put-Klasse

Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von numerischen Werten in Sequenzen vom Typ `CharType` zu steuern.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>Parameter

`CharType` Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.

`OutputIterator` Der Typ eines Iterators, der die numerischen-Funktionen PUT, ihre Ausgabe schreiben.

## <a name="remarks"></a>Hinweise

Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **id** gespeichert.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[num_put](#num_put)|Der Konstruktor für Objekte des Typs `num_put`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|
|[iter_type](#iter_type)|Ein Typ, der einen Ausgabeiterator beschreibt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[do_put](#do_put)|Eine virtuelle Funktion, die aufgerufen wird, um eine Zahl in eine Sequenz von `CharType`-Objekten zu konvertieren, die die Zahl darstellt, die für ein bestimmtes Gebietsschema formatiert ist.|
|[put](#put)|Konvertiert eine Zahl in eine Sequenz von `CharType`-Objekten, die die Zahl darstellt, die für ein bestimmtes Gebietsschema formatiert wird.|

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="char_type"></a> num_put::char_type

Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter **CharType** dar.

## <a name="do_put"></a> num_put::do_put

Eine virtuelle Funktion, die aufgerufen wird, um eine Zahl in eine Sequenz von **CharType**s zu konvertieren, die die Zahl darstellt, die für ein bestimmtes Gebietsschema formatiert ist.

```cpp
virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const unsigned long long val) const;
```

### <a name="parameters"></a>Parameter

`next` Ein Iterator, der das erste Element der eingefügten Zeichenfolge.

`_Iosbase` Den Datenstrom enthält Gebietsschema mit Numpunct Facets verwendet, um die Ausgabe und die Flags für das Formatieren der Ausgabe Satzzeichen voneinander getrennt wird angegeben.

`_Fill` Ein Zeichen, die für die Analyse verwendet wird.

`val` Die Anzahl oder ein Boolean-Typ ausgegeben werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der auf die erste Position nach dem jeweils letzten Element verweist.

### <a name="remarks"></a>Hinweise

Die erste geschützte virtuelle Memberfunktion generiert sequenzielle Elemente ab `next`, um ein Ausgabefeld für eine ganze Zahl für den Wert von `val` zu erzeugen. Die Funktion gibt einen Iterator zurück, der die nächste Stelle zum Einfügen eines Elements nach dem generierten Ausgabefeld für ganze Zahlen festlegt.

Die Ausgabefeld für ganze Zahlen wird mit den gleichen Regeln generiert, die von Druckfunktionen für das Generieren einer Serie an `char`-Elementen in einer Datei verwendet wurden. Jedes dieser char-Elemente soll einem äquivalenten Element vom Typ **CharType** durch eine einfache 1:1-Zuordnung zugeordnet werden. Wenn eine Druckfunktion ein Feld mit Leerzeichen oder der Ziffer 0 auffüllt, jedoch wird `do_put` anstatt **fill** verwendet. Die entsprechende Druckkonvertierungsspezifikation wird wie folgt bestimmt:

- Wenn **iosbase**. [flags](../standard-library/ios-base-class.md#flags) & `ios_base::basefield` == `ios_base::`[oct](../standard-library/ios-functions.md#oct), ist die Konvertierungsangabe **lo**.

- Wenn **iosbase.flags** & **ios_base::basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex), ist die Konvertierungsspezifikation **lx**.

- Andernfalls ist die Konvertierungsspezifikation **ld**

Wenn **iosbase**. [width](../standard-library/ios-base-class.md#width) ungleich null ist, wird eine Feldbreite dieses Werts vorangestellt. Die Funktion ruft **iosbase**. **width**(0) auf, um die Feldbreite auf null zurückzusetzen.

Auffüllung erfolgt nur, wenn die minimale Anzahl von Elementen *N*, die zur Angabe des Ausgabefelds erforderlich ist, kleiner als **iosbase**. [width](../standard-library/ios-base-class.md#width) ist. Auffüllen von Feldern besteht aus einer Sequenz von *N* - **Breite** Kopien **Füllung**. Das Auffüllen erfolgt folgendermaßen:

- Wenn **iosbase**. **Flags** & `ios_base::adjustfield` == `ios_base::`[linken](../standard-library/ios-functions.md#left), das Flag **-** vorangestellt ist. (Abstand tritt nach dem generierten Text auf.)

- Wenn **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[internal](../standard-library/ios-functions.md#internal), dann wird das Flag **0** vorangestellt. (Für ein numerisches Ausgabefeld tritt der Abstand dort auf, wo die Druckfunktionen mit 0 auffüllen.)

- Andernfalls wird kein zusätzliches Flag vorangestellt. (Abstand tritt vor der generierten Sequenz auf.)

Zum Schluss:

- Wenn **iosbase**. **flags** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) ungleich null ist, wird das Flag **+** der Konvertierungsspezifikation vorangestellt.

- Wenn **iosbase**. **flags** & **ios_base::**[showbase](../standard-library/ios-functions.md#showbase) ungleich null ist, wird das Flag **#** der Konvertierungsspezifikation vorangestellt.

Das Format eines Ausgabefelds für ganze Zahlen hängt darüber hinaus von der [localefacet](../standard-library/locale-class.md#facet_class)**fac** ab, die vom Aufruf [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase** zurückgegeben wird. [getloc](../standard-library/ios-base-class.md#getloc)). Dies gilt insbesondere in folgenden Fällen:

- **fac**. [grouping](../standard-library/numpunct-class.md#grouping) bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) bestimmt die Sequenz, die Gruppen von Ziffern auf der linken Seite eines Dezimaltrennzeichens trennt.

Erfolgen keine Gruppierungseinschränkungen durch **fac**. **grouping** (sein erstes Element weist den Wert CHAR_MAX auf), werden keine Instanzen von **fac**. `thousands_sep` im Ausgabefeld generiert. Andernfalls werden Trennzeichen eingefügt, nachdem die Druckkonvertierung erfolgt.

Die zweite virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

verhält sich wie die erste, außer dass sie eine Konvertierungsspezifikation von **ld** mit **lu** ersetzt.

Die dritte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

verhält sich wie die erste, außer dass sie ein Gleitkommaausgabefeld aus dem Wert **val** erzeugt. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) bestimmt die Sequenz, die ganzzahlige Ziffern von Bruchziffern trennt. Die entsprechende Druckkonvertierungsspezifikation wird wie folgt bestimmt:

- Wenn **iosbase**. **flags** & `ios_base::floatfield` == `ios_base::`[fixed](../standard-library/ios-functions.md#fixed), ist die Konvertierungsangabe **lf**.

- Wenn **iosbase**. **flags** & **ios_base::floatfield** == `ios_base::`[scientific](../standard-library/ios-functions.md#scientific), ist die Konvertierungsspezifikation `le`. Wenn **iosbase**. **flags** & `ios_base::`[uppercase](../standard-library/ios-functions.md#uppercase) ungleich null ist, wird **e** durch **E** ersetzt.

- Andernfalls ist die Konvertierungsspezifikation **lg**. Wenn **iosbase**. **flags** & **ios_base::uppercase** ungleich null ist, wird **g** durch **G** ersetzt.

Wenn **iosbase**. **flags** & **ios_base::fixed** ungleich null ist oder wenn **iosbase**. [precision](../standard-library/ios-base-class.md#precision) größer als null ist, wird eine Genauigkeit mit dem Wert **iosbase**. **precision** der Konvertierungsspezifikation vorangestellt. Abstände verhalten sich genauso wie bei einem Ausgabefeld für ganze Zahlen. Das Füllzeichen ist **fill**. Zum Schluss:

- Wenn **iosbase**. **flags** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) ungleich null ist, wird das Flag **+** der Konvertierungsspezifikation vorangestellt.

- Wenn **iosbase**. **flags** & `ios_base::`[showpoint](../standard-library/ios-functions.md#showpoint) ungleich null ist, wird das Flag **#** der Konvertierungsspezifikation vorangestellt.

Die vierte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

verhält sich wie die dritte, außer dass der Qualifizierer **l** bei der Konvertierungsspezifikation durch **L** ersetzt wird.

Die fünfte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

verhält sich wie die erste, außer dass die Konvertierungsspezifikation `p`**,** sowie alle Qualifizierer Abstand angeben müssen.

Die sechste virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

verhält sich wie die erste, generiert jedoch ein boolesches Ausgabefeld aus `val`.

Ein boolesches Ausgabefeld nimmt eine von zwei Formen an. Wenn **iosbase**. **flags** & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) **falsch** ist, gibt die Memberfunktion `do_put`(_ *Next*, \_ *Iosbase*, \_ *Fill*, ( **long**) `val`) zurück, was in der Regel eine generierte Sequenz von 0 (für **FALSE**) oder 1 (für **TRUE**) erstellt. Andernfalls ist die generierte Sequenz entweder **fac**. [falsename](../standard-library/numpunct-class.md#falsename)`)` (für **FALSE**), oder **fac**. [truename](../standard-library/numpunct-class.md#truename) (für **TRUE**) übereinstimmen.

Die siebte virtuelle geschützte Memberfunktion:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

verhält sich wie die erste, außer dass sie eine Konvertierungsspezifikation von **ld** durch **lld** ersetzt.

Die achte virtuell, geschützte Memberfunktion:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

verhält sich wie die erste, außer dass sie eine Konvertierungsspezifikation von `ld` durch `llu` ersetzt.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [put](#put), mit dem `do_put` aufgerufen wird.

## <a name="iter_type"></a> num_put::iter_type

Ein Typ, der einen Ausgabeiterator beschreibt.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Vorlagenparameter **OutputIterator**.

## <a name="num_put"></a> num_put::num_put

Der Konstruktor für Objekte des Typs `num_put`.

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parameter

`_Refs` Integer-Wert verwendet, um den Typ der Verwaltung des Arbeitsspeichers für das Objekt angeben.

### <a name="remarks"></a>Hinweise

Mögliche Werte für den `_Refs`-Parameter und ihre Bedeutung:

- 0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.

- 1: Die Lebensdauer des Objekts muss manuell verwaltet werden.

- \> 1: Diese Werte sind nicht definiert.

Direkte Beispiele hierfür sind nicht möglich, da der Destruktor geschützt ist.

Der Konstruktor initialisiert sein Basisobjekt mit **locale::**[facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).

## <a name="put"></a> num_put::put

Konvertiert eine Zahl in eine Sequenz von **CharType**s, die die Zahl darstellt, die für ein bestimmtes Gebietsschema formatiert wird.

```cpp
iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Long long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Unsigned long long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;
```

### <a name="parameters"></a>Parameter

`dest` Ein Iterator, der das erste Element der eingefügten Zeichenfolge.

`_Iosbase` Angegeben, den Stream, der mit dem Numpunct-Facet verwendet, um die Ausgabe und die Flags für das Formatieren der Ausgabe Satzzeichen voneinander getrennt Gebietsschema enthält.

`_Fill` Ein Zeichen, die für die Analyse verwendet wird.

`val` Die Anzahl oder ein Boolean-Typ ausgegeben werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der auf die erste Position nach dem jeweils letzten Element verweist.

### <a name="remarks"></a>Hinweise

Beide Memberfunktionen geben [do_put](#do_put)( `next`, `_Iosbase`, `_Fill`, `val`) zurück.

### <a name="example"></a>Beispiel

```cpp
// num_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );
   basic_stringstream<char> psz2;
   ios_base::iostate st = 0;
   long double fVal;
   cout << "The thousands separator is: "
        << use_facet < numpunct <char> >(loc).thousands_sep( )
        << endl;

   psz2.imbue( loc );
   use_facet < num_put < char > >
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),
                    psz2, ' ', fVal=1000.67);

   if ( st & ios_base::failbit )
      cout << "num_put( ) FAILED" << endl;
   else
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;
}
```

```Output
The thousands separator is: .
num_put( ) = 1.000,67
```

## <a name="see-also"></a>Siehe auch

[\<locale>](../standard-library/locale.md)<br/>
[Facet-Klasse](../standard-library/locale-class.md#facet_class)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
