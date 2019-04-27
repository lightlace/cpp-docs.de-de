---
title: istrstream-Klasse
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: 70e71ac5a6fd523f0b7589625f4e88fdb41ee0e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224272"
---
# <a name="istrstream-class"></a>istrstream-Klasse

Beschreibt ein Objekt, das die Extraktion von Elementen und codierten Objekten aus einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.

## <a name="syntax"></a>Syntax

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Hinweise

Das Objekt speichert ein Objekt der Klasse `strstreambuf`.

> [!NOTE]
> Diese Klasse ist veraltet. Verwenden Sie stattdessen [istringstream](../standard-library/sstream-typedefs.md#istringstream) oder [wistringstream](../standard-library/sstream-typedefs.md#wistringstream).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[istrstream](#istrstream)|Konstruiert ein Objekt vom Typ `istrstream`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[rdbuf](#rdbuf)|Gibt einen Zeiger auf das dem Stream zugeordnete `strstreambuf`-Objekt zurück.|
|[str](#str)|Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<strstream>

**Namespace:** std

## <a name="istrstream"></a> istrstream::istrstream

Konstruiert ein Objekt vom Typ `istrstream`.

```cpp
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```

### <a name="parameters"></a>Parameter

*count*<br/>
Die Länge des Puffers (*Ptr*).

*ptr*<br/>
Der Inhalt, mit dem der Puffer initialisiert wird.

### <a name="remarks"></a>Hinweise

Alle Konstruktoren initialisieren die Basisklasse durch Aufrufen von [Istream](../standard-library/istream-typedefs.md#istream)(**Sb**), wobei `sb` das gespeicherte Objekt der Klasse [Strstreambuf](../standard-library/strstreambuf-class.md). Die ersten beiden Konstruktoren initialisieren auch `sb` durch Aufrufen von `strstreambuf`(( **const** `char` \*) `ptr`, 0). Stattdessen rufen die verbleibenden beiden Konstruktoren `strstreambuf`((**const**`char` *) `ptr`, `count`) auf.

## <a name="rdbuf"></a> istrstream::rdbuf

Gibt einen Zeiger auf das dem Stream zugeordneten strstreambuf-Objekt zurück.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Adresse des gespeicherten Streampuffers des Typs Zeiger auf [strstreambuf](../standard-library/strstreambuf-class.md) zurück.

### <a name="example"></a>Beispiel

Unter [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) finden Sie ein Beispiel, das `rdbuf` verwendet.

## <a name="str"></a> istrstream::str

Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf und gibt anschließend einen Zeiger auf den Anfang der kontrollierten Sequenz zurück.

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

[istream](../standard-library/istream-typedefs.md#istream)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
