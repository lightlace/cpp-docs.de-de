---
title: basic_ostringstream-Klasse
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
ms.openlocfilehash: aa25c379e47bbe22efc78d65b3f6745e98098cbd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453508"
---
# <a name="basicostringstream-class"></a>basic_ostringstream-Klasse

Beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> steuert.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parameter

*Zuordnungseinheits*\
Die Zuweisungsklasse.

*Elem*\
Der Typ des grundlegenden Elements der Zeichenfolge.

*Stadtrat*\
Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer mit Elementen des `Elem`Typs steuert, dessen Zeichen Merkmale durch die- `Tr`Klasse bestimmt sind und deren Elemente von einer Zuweisung von zugewiesen werden. - `Alloc`Klasse. Das Objekt speichert ein Objekt der Klasse basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Konstruiert ein Objekt vom Typ `basic_ostringstream`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Der Typ ist ein Synonym für den Vorlagen Parameter " *Zuweisung*".|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[rdbuf](#rdbuf)|Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` an [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> zurück.|
|[str](#str)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|

## <a name="requirements"></a>Anforderungen

**Header:** \<sstream>

**Namespace:** std

## <a name="allocator_type"></a> basic_ostringstream::allocator_type

Der Typ ist ein Synonym für den Vorlagen Parameter " *Zuweisung*".

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstream"></a> basic_ostringstream::basic_ostringstream

Konstruiert ein Objekt vom Typ „basic_ostringstream“.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parameter

*_Mode*\
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*SRT*\
Ein Objekt vom Typ `basic_string`.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisklasse durch Aufrufen [von Basic_ostream](../standard-library/basic-ostream-class.md)( **SB**), `sb` wobei das gespeicherte Objekt der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **TR**, `Alloc`> ist. Er initialisiert außerdem **sb** durch Aufruf von basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode` &#124; `ios_base::out`).

Der zweite Konstruktor initialisiert die Basisklasse durch Aufrufen von basic_ostream( **sb**). Sie `sb` initialisiert auch durch Aufrufen von Basic_stringbuf < **Elem**, **TR** `Alloc`> (_ *Str*, `_Mode` &#124; `ios_base::out`).

## <a name="rdbuf"></a> basic_ostringstream::rdbuf

Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` an [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **TR**, `Alloc`> zurück.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des `pointer` gespeicherten Streampuffers des Typs in Basic_stringbuf < **Elem**, **TR** `Alloc`>.

### <a name="remarks"></a>Hinweise

Die Member-Funktion gibt die Adresse des gespeicherten Streampuffers des `pointer` Typs an Basic_stringbuf < **Elem**, **TR** `Alloc`> zurück.

### <a name="example"></a>Beispiel

Sie finden ein Beispiel, in dem `rdbuf` verwendet wird, unter [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="str"></a> basic_ostringstream::str

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
