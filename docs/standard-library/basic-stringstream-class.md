---
title: basic_stringstream-Klasse
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
ms.openlocfilehash: 9278b6ce0fa23fa875f1af57ea15719111439372
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447808"
---
# <a name="basicstringstream-class"></a>basic_stringstream-Klasse

Beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten mit einem Streampuffer der Klasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> steuert.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parameter

*Zuordnungseinheits*\
Die Zuweisungsklasse.

*Elem*\
Der Typ des grundlegenden Elements der Zeichenfolge.

*Stadtrat*\
Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.

## <a name="remarks"></a>Hinweise

Die Vorlagen Klasse beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten mit einem Streampuffer der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, `Alloc` **TR**, > und Elementen des Typs steuert.`Elem`, dessen Zeichen Merkmale durch die-Klasse `Tr`bestimmt werden und deren Elemente von einer Zuweisung der-Klasse `Alloc`zugeordnet werden. Das Objekt speichert ein Objekt der Klasse basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_stringstream](#basic_stringstream)|Konstruiert ein Objekt vom Typ `basic_stringstream`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[rdbuf](#rdbuf)|Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` an [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> zurück.|
|[str](#str)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|

## <a name="requirements"></a>Anforderungen

**Header:** \<sstream>

**Namespace:** std

## <a name="allocator_type"></a> basic_stringstream::allocator_type

Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstream"></a> basic_stringstream::basic_stringstream

Konstruiert ein Objekt vom Typ `basic_stringstream`.

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Mode*\
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*SRT*\
Ein Objekt vom Typ `basic_string`.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisklasse durch Aufrufen [von basic_iostream](../standard-library/basic-iostream-class.md)( **SB**), `sb` wobei das gespeicherte Objekt der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **TR**, `Alloc`> ist. Sie `sb` initialisiert auch durch Aufrufen von Basic_stringbuf **< Elem**, **TR** `Alloc`> ( `_Mode`).

Der zweite Konstruktor initialisiert die Basisklasse durch Aufruf von basic_iostream( **sb**). Sie initialisiert `sb` auch durch Aufrufen von Basic_stringbuf < **Elem**, **TR** `Alloc`> (_ *Str*, `_Mode`).

## <a name="rdbuf"></a> basic_stringstream::rdbuf

Gibt die Adresse des gespeicherten Streampuffers des Typs **pointer** zurück, die ein Zeiger auf [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> ist.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des gespeicherten Streampuffers des Typs `pointer` in Basic_stringbuf < **Elem**, **TR** `Alloc`>.

### <a name="example"></a>Beispiel

Sie finden ein Beispiel, in dem `rdbuf` verwendet wird, unter [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="str"></a> basic_stringstream::str

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

Gibt ein Objekt der Klasse [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> zurück, dessen gesteuerte Sequenz eine Kopie der von **\*this** gesteuerten Sequenz ist.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion gibt [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str) zurück. Die zweite Memberfunktion ruft `rdbuf` -> **str**( `_Newstr`) auf.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung `str`von finden Sie unter [Basic_stringbuf:: Str](../standard-library/basic-stringbuf-class.md#str) .

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
