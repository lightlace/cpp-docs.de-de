---
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: 3f1fb202692d09fa87eb775677e46e1c3f36dbad
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688945"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

Definiert mehrere Klassen Vorlagen, die Iostreams-Vorgänge für Sequenzen unterstützen, die in einem zugeordneten Array Objekt gespeichert sind. Solche Sequenzen können problemlos in und aus Objekten der Klassen Vorlage [basic_string](../standard-library/basic-string-class.md)konvertiert werden.

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

Objekte vom Typ `char *` können die Funktionalität in [\<strstream >](../standard-library/strstream.md) für das Streaming verwenden. @No__t_0strstream > ist jedoch veraltet, und die Verwendung \<sstream > wird empfohlen.

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Erstellt einen Typ `basic_istringstream` der auf einen **char** -Vorlagen Parameter spezialisiert ist.|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Erstellt einen Typ `basic_ostringstream` der auf einen **char** -Vorlagen Parameter spezialisiert ist.|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Erstellt einen Typ `basic_stringbuf` der auf einen **char** -Vorlagen Parameter spezialisiert ist.|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Erstellt einen Typ `basic_stringstream` der auf einen **char** -Vorlagen Parameter spezialisiert ist.|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Erstellt einen Typ `basic_istringstream` der auf einen **wchar_t** Template-Parameter spezialisiert ist.|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Erstellt einen Typ `basic_ostringstream` der auf einen **wchar_t** Template-Parameter spezialisiert ist.|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Erstellt einen Typ `basic_stringbuf` der auf einen **wchar_t** Template-Parameter spezialisiert ist.|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Erstellt einen Typ `basic_stringstream` der auf einen **wchar_t** Template-Parameter spezialisiert ist.|

### <a name="manipulators"></a>Manipulatoren

|||
|-|-|
|[swap](../standard-library/sstream-functions.md#sstream_swap)|Tauscht die Werte zwischen zwei `sstream`-Objekten aus.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Beschreibt einen die Übertragung zu und aus einer Sequenz von in einem Arrayobjekt gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|Beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**Elem**, **TR**, `Alloc` > mit Elementen des Typs `Elem` steuert, dessen Zeichen Merkmale von bestimmt werden. die Klasse `Tr` und deren Elemente durch eine Zuweisung der Klasse `Alloc` zugeordnet werden.|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**Elem**, **TR**, `Alloc` > mit Elementen des Typs `Elem` steuert, dessen Zeichen Merkmale durch die Klassen `Tr` und deren Elemente durch eine Zuweisung der Klasse `Alloc` zugeordnet werden.|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten mit einem Streampuffer der Klasse [Basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**Elem**, **TR**, `Alloc` > mit Elementen vom Typ `Elem` steuert, dessen Zeichen Merkmale wird durch die-Klasse `Tr` und deren Elemente durch eine Zuweisung der Klasse `Alloc` zugeordnet.|

## <a name="requirements"></a>Anforderungen

- **Header:** \<sstream>

- **Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
