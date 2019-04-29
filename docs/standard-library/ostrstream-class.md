---
title: ostrstream-Klasse
ms.date: 11/04/2016
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
ms.openlocfilehash: 2d4a7a780f1a7db27bcb600c13430deaa0dc35cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370867"
---
# <a name="ostrstream-class"></a>ostrstream-Klasse

Beschreibt ein Objekt, das das Einfügen von Elementen und programmierten Objekten in einen Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.

## <a name="syntax"></a>Syntax

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Hinweise

Das Objekt speichert ein Objekt der Klasse `strstreambuf`.

> [!NOTE]
> Diese Klasse ist veraltet. Verwenden Sie stattdessen [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) oder [wostringstream](../standard-library/sstream-typedefs.md#wostringstream).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[ostrstream](#ostrstream)|Konstruiert ein Objekt vom Typ `ostrstream`.|

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

## <a name="freeze"></a> ostrstream::freeze

Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parameter

*_Freezeit*<br/>
Ein **"bool"** , der angibt, ob den Stream fixiert werden soll.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*) auf.

### <a name="example"></a>Beispiel

Finden Sie unter [strstream:: Freeze](../standard-library/strstreambuf-class.md#freeze) für ein Beispiel, verwendet `freeze`.

## <a name="ostrstream"></a> ostrstream::ostrstream

Konstruiert ein Objekt vom Typ `ostrstream`.

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Der Puffer.

*count*<br/>
Die Größe des Puffers in Byte.

*_Mode*<br/>
Der Eingabe- und Ausgabemodus des Puffers. Weitere Informationen finden Sie unter [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

### <a name="remarks"></a>Hinweise

Beide Konstruktoren initialisieren die Basisklasse durch Aufrufen von [Ostream](../standard-library/ostream-typedefs.md#ostream)(**Sb**), wobei `sb` das gespeicherte Objekt der Klasse [Strstreambuf](../standard-library/strstreambuf-class.md). Der erste Konstruktor initialisiert zudem `sb` durch Aufrufen von `strstreambuf`. Der zweite Konstruktor initialisiert die Basisklasse auf eine von zwei Arten:

- Wenn `_Mode`  &  **ios_base:: trunc**== 0, dann `ptr` müssen festlegen, das erste Element eines Arrays von `count` Elemente und der Konstruktor ruft `strstreambuf`(`ptr`, `count`, `ptr`).

- Andernfalls `ptr` müssen festlegen, das erste Element eines Arrays an Count-Elementen, die eine C-Zeichenfolge enthält, deren erstes Element erhalten Sie, `ptr`, und der Konstruktor ruft `strstreambuf`(`ptr`, `count`, `ptr` + `strlen`( `ptr`) ).

## <a name="pcount"></a> ostrstream::pcount

Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente, die in die kontrollierte Sequenz geschrieben wurden.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount) zurück.

### <a name="example"></a>Beispiel

Siehe [strstream::pcount](../standard-library/strstreambuf-class.md#pcount) für ein Beispiel, das `pcount` verwendet.

## <a name="rdbuf"></a> ostrstream::rdbuf

Gibt einen Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt zurück.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` zu [Strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Beispiel

Ein Beispiel, das `rdbuf` verwendet, finden Sie unter [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="str"></a> ostrstream::str

Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf und gibt anschließend einen Zeiger zum Anfang der kontrollierten Sequenz zurück.

```cpp
char *str();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den Anfang der kontrollierten Sequenz.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) zurück.

### <a name="example"></a>Beispiel

Finden Sie unter [strstream:: str](../standard-library/strstreambuf-class.md#str) für ein Beispiel, verwendet `str`.

## <a name="see-also"></a>Siehe auch

[ostream](../standard-library/ostream-typedefs.md#ostream)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
