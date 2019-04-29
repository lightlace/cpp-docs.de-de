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
ms.openlocfilehash: 45a7eb1384c70b488e057fb9df8ad4c496272316
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414138"
---
# <a name="basicostringstream-class"></a>basic_ostringstream-Klasse

Beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> steuert.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parameter

*Alloc*<br/>
Die Zuweisungsklasse.

*Elem*<br/>
Der Typ des grundlegenden Elements der Zeichenfolge.

*Tr*<br/>
Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das steuert, Einfügen von Elementen und codierten Objekten in einen Streampuffer mit Elementen des Typs `Elem`, dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`, und, dessen Elemente durch eine Zuweisung der zugeordnet werden Klasse `Alloc`. Das Objekt speichert ein Objekt der Klasse basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Konstruiert ein Objekt vom Typ `basic_ostringstream`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Der Typ ist ein Synonym für den Vorlagenparameter *Alloc*.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[rdbuf](#rdbuf)|Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` an [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> zurück.|
|[str](#str)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|

## <a name="requirements"></a>Anforderungen

**Header:** \<sstream>

**Namespace:** std

## <a name="allocator_type"></a> basic_ostringstream::allocator_type

Der Typ ist ein Synonym für den Vorlagenparameter *Alloc*.

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

*_Mode*<br/>
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*<br/>
Ein Objekt vom Typ `basic_string`.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisklasse durch Aufrufen von [Basic_ostream](../standard-library/basic-ostream-class.md)( **Sb**), wobei `sb` das gespeicherte Objekt der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**, **Tr**, `Alloc`>. Er initialisiert außerdem **sb** durch Aufruf von basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode` &#124; `ios_base::out`).

Der zweite Konstruktor initialisiert die Basisklasse durch Aufrufen von basic_ostream( **sb**). Er initialisiert zudem `sb` durch Aufruf von Basic_stringbuf < **Elem**, **Tr**, `Alloc`> (_ *Str*, `_Mode` &#124; `ios_base::out`).

## <a name="rdbuf"></a> basic_ostringstream::rdbuf

Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` zu [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des gespeicherten Streampuffers des Typs `pointer` basic_stringbuf < **Elem**, **Tr**, `Alloc`>.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` basic_stringbuf < **Elem**, **Tr**, `Alloc`>.

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

*_Newstr*<br/>
Die neue Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Gibt ein Objekt der Klasse [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> zurück, dessen gesteuerte Sequenz eine Kopie der von **\*this** gesteuerten Sequenz ist.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion gibt [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str) zurück. Die zweite Memberfunktion ruft `rdbuf` -> **str**( `_Newstr`) auf.

### <a name="example"></a>Beispiel

Finden Sie unter [basic_stringbuf:: str](../standard-library/basic-stringbuf-class.md#str) für ein Beispiel, verwendet `str`.

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
