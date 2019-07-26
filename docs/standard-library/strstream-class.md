---
title: strstream-Klasse
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
ms.openlocfilehash: 53baa350121796d5198211e1fdb08f4341df6b80
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459105"
---
# <a name="strstream-class"></a>strstream-Klasse

Beschreibt ein Objekt, das die Einfügung und Extraktion von Elementen und codierten Objekten mit einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.

## <a name="syntax"></a>Syntax

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Hinweise

Das Objekt speichert ein Objekt der Klasse `strstreambuf`.

> [!NOTE]
> Diese Klasse ist veraltet. Verwenden Sie stattdessen [stringstream](../standard-library/sstream-typedefs.md#stringstream) oder [wstringstream](../standard-library/sstream-typedefs.md#wstringstream).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[strstream](#strstream)|Konstruiert ein Objekt vom Typ `strstream`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[freeze](#freeze)|Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.|
|[pcount](#pcount)|Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.|
|[rdbuf](#rdbuf)|Gibt einen Zeiger auf das dem Stream zugeordnete `strstreambuf`-Objekt zurück.|
|[str](#str)|Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<strstream>

**Namespace:** std

## <a name="freeze"></a> strstream::freeze

Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parameter

*_Freezeit*\
Ein  boolescher Wert, der angibt, ob der Stream eingefroren werden soll.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*) auf.

### <a name="example"></a>Beispiel

Unter " [straustreambuf:: Freeze](../standard-library/strstreambuf-class.md#freeze) " finden Sie ein `freeze`Beispiel, das verwendet.

## <a name="pcount"></a> strstream::pcount

Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente, die in die kontrollierte Sequenz geschrieben wurden.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount) zurück.

### <a name="example"></a>Beispiel

Unter [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) finden Sie ein Beispiel, das pcount verwendet.

## <a name="rdbuf"></a> strstream::rdbuf

Gibt einen Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt zurück.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt.

### <a name="remarks"></a>Hinweise

Die Member-Funktion gibt die Adresse des gespeicherten Streampuffers des `pointer` Typs in " [straustreambuf](../standard-library/strstreambuf-class.md)" zurück.

### <a name="example"></a>Beispiel

Unter [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) finden Sie ein Beispiel, das `rdbuf` verwendet.

## <a name="str"></a> strstream::str

Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf und gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.

```cpp
char *str();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den Anfang der kontrollierten Sequenz.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) zurück.

### <a name="example"></a>Beispiel

Unter " [straustreambuf:: Str](../standard-library/strstreambuf-class.md#str) " finden Sie ein `str`Beispiel, das verwendet.

## <a name="strstream"></a> strstream::strstream

Konstruiert ein Objekt vom Typ `strstream`.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*Countdown*\
Die Größe des Puffers.

*_Mode*\
Der Eingabe- und Ausgabemodus des Puffers. Weitere Informationen finden Sie unter [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*PTR*\
Der Puffer.

### <a name="remarks"></a>Hinweise

Beide Konstruktoren initialisieren die Basisklasse durch Aufrufen von [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **SB**), `sb` wobei das gespeicherte Objekt der Klasse "" von " [strauf](../standard-library/strstreambuf-class.md)" ist. Der erste Konstruktor wird auch durch `sb` Aufrufen von " [straustreambuf](../standard-library/strstreambuf-class.md#strstreambuf)" initialisiert. Der zweite Konstruktor initialisiert die Basisklasse auf eine von zwei Arten:

- Wenn `_Mode` `strstreambuf` `ptr` `count` `count` `ptr`  ios_base:: App = = 0, dann muss PTR das erste Element eines Arrays von Elementen festlegen, und der Konstruktor ruft (,,) auf.  &  .

- Andernfalls muss *ptr* das erste Element eines Arrays von count-Elementen festlegen, das eine C-Zeichenfolge enthält, deren erstes Element *von PTR*festgelegt wird, und `strstreambuf`der `ptr`Konstruktor ruft (,, `ptr` `count`  +  `strlen`( `ptr`) ).

## <a name="see-also"></a>Siehe auch

[iostream](../standard-library/istream-typedefs.md#iostream)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
