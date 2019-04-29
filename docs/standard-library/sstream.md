---
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: cc08fb426df289b3478ad9d29b03f9a6dd5d3978
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412474"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

Definiert mehrere Vorlagenklassen, die iostreams-Vorgänge für Sequenzen unterstützen, die in einem reservierten Array-Objekt gespeichert werden. Solche Sequenzen können auf einfache Weise in und aus Objekten der Vorlagenklasse [basic_string](../standard-library/basic-string-class.md) konvertiert werden.

## <a name="syntax"></a>Syntax

```cpp
namespace std {
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringbuf;
typedef basic_stringbuf<char>
stringbuf;
typedef basic_stringbuf<wchar_t> wstringbuf;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_istringstream;
typedef basic_istringstream<char>
istringstream;
typedef basic_istringstream<wchar_t> wistringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_ostringstream;
typedef basic_ostringstream<char>
ostringstream;
typedef basic_ostringstream<wchar_t> wostringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringstream;
typedef basic_stringstream<char>
stringstream;
typedef basic_stringstream<wchar_t> wstringstream;
// TEMPLATE FUNCTIONS
template <class CharType, class Traits, class Allocator>
void swap(
    basic_stringbuf<CharType, Traits, Allocator>& left,
    basic_stringbuf<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_istringstream<CharType, Traits, Allocator>& left,
    basic_istringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_ostringstream<CharType, Traits, Allocator>& left,
    basic_ostringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap (
    basic_stringstream<CharType, Traits, Allocator>& left,
    basic_stringstream<CharType, Traits, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Verweis auf ein `sstream`-Objekt.|
|*right*|Ein Verweis auf ein `sstream`-Objekt.|

## <a name="remarks"></a>Hinweise

Objekte vom Typ `char *` können die Funktionalität in [\<strstream >](../standard-library/strstream.md) für das Streaming verwenden. Allerdings \<Strstream > ist veraltet und die Verwendung von \<Sstream > wird empfohlen.

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Erstellt einen Typ `basic_istringstream` auf eine **Char** Template-Parameter.|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Erstellt einen Typ `basic_ostringstream` auf eine **Char** Template-Parameter.|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Erstellt einen Typ `basic_stringbuf` auf eine **Char** Template-Parameter.|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Erstellt einen Typ `basic_stringstream` auf eine **Char** Template-Parameter.|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Erstellt einen Typ `basic_istringstream` auf eine **"wchar_t"** Template-Parameter.|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Erstellt einen Typ `basic_ostringstream` auf eine **"wchar_t"** Template-Parameter.|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Erstellt einen Typ `basic_stringbuf` auf eine **"wchar_t"** Template-Parameter.|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Erstellt einen Typ `basic_stringstream` auf eine **"wchar_t"** Template-Parameter.|

### <a name="manipulators"></a>Manipulatoren

|||
|-|-|
|[swap](../standard-library/sstream-functions.md#sstream_swap)|Tauscht die Werte zwischen zwei `sstream`-Objekten aus.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Beschreibt einen die Übertragung zu und aus einer Sequenz von in einem Arrayobjekt gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|Beschreibt ein Objekt, das steuert, Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, mit Elementen des Typs `Elem`, dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`, und es werden, dessen Elemente durch eine Zuweisung der Klasse zugeordnet `Alloc`.|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Beschreibt ein Objekt, das steuert, Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, mit Elementen des Typs `Elem`, dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`, und es werden, dessen Elemente durch eine Zuweisung der Klasse zugeordnet `Alloc`.|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Beschreibt ein Objekt, das steuert, Einfügung und Extraktion von Elementen und codierten Objekten mit einem Streampuffer der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`>, mit Elementen des Typs `Elem`, dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`, und es werden, dessen Elemente durch eine Zuweisung der Klasse zugeordnet `Alloc`.|

## <a name="requirements"></a>Anforderungen

- **Header:** \<sstream>

- **Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
