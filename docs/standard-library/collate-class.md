---
title: collate-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::collate
- locale/std::collate::char_type
- locale/std::collate::string_type
- locale/std::collate::compare
- locale/std::collate::do_compare
- locale/std::collate::do_hash
- locale/std::collate::do_transform
- locale/std::collate::hash
- locale/std::collate::transform
dev_langs:
- C++
helpviewer_keywords:
- std::collate [C++]
- std::collate [C++], char_type
- std::collate [C++], string_type
- std::collate [C++], compare
- std::collate [C++], do_compare
- std::collate [C++], do_hash
- std::collate [C++], do_transform
- std::collate [C++], hash
- std::collate [C++], transform
ms.assetid: 92168798-9628-4a2e-be6e-fa62dcd4d6a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 054246ce78601abf61f36d070500845275b61761
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110372"
---
# <a name="collate-class"></a>collate-Klasse

Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um die Reihenfolge und Gruppierung der Zeichen in einer Zeichenfolge, Vergleiche zwischen ihnen und das Hashing von Zeichenfolgen zu steuern.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType>
class collate : public locale::facet;
```

### <a name="parameters"></a>Parameter

*CharType*<br/>
Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.

## <a name="remarks"></a>Hinweise

Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in `id` gespeichert. In einigen Sprachen werden Zeichen gruppiert und als einzelnes Zeichen behandelt. In anderen Sprachen hingegen werden einzelne Zeichen als zwei Zeichen behandelt. Die sortierenden Dienste, die von der collate-Klasse bereitgestellt werden, bieten die Möglichkeit zum Sortieren dieser Fälle.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[collate](#collate)|Der Konstruktor für Objekte der `collate`-Klasse, die als Gebietsschemafacet dient, um Zeichenfolgensortierungskonventionen zu bearbeiten.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Ein Typ, der ein Zeichen vom Typ `CharType` beschreibt.|
|[string_type](#string_type)|Ein Typ, der eine Zeichenfolge vom Typ `basic_string` beschreibt, die Zeichen vom Typ `CharType` enthält.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[compare](#compare)|Vergleicht zwei Zeichensequenzen nach ihren facetspezifischen Regeln für Gleichheit oder Ungleichheit.|
|[do_compare](#do_compare)|Eine virtuelle Funktion, die aufgerufen wird, um zwei Zeichensequenzen gemäß ihren facetspezifischen Regeln in Bezug auf Gleichheit oder Ungleichheit zu vergleichen.|
|[do_hash](#do_hash)|Eine virtuelle Funktion, die aufgerufen wird, um den Hashwert der Sequenzen anhand der facetspezifischen Regeln zu bestimmen.|
|[do_transform](#do_transform)|Eine virtuelle Funktion, die aufgerufen wird, um eine Zeichenfolge aus einem Gebietsschema in eine Zeichenfolge zu konvertieren, die in den lexikografischen Vergleichen mit anderen Zeichensequenzen verwendet werden kann, die auf ähnliche Weise aus demselben Gebietsschema konvertiert wurden.|
|[hash](#hash)|Bestimmt den Hashwert der Sequenz nach ihren facetspezifischen Regeln.|
|[transform](#transform)|Konvertiert eine Zeichenfolge von einem Gebietsschema in eine Zeichenfolge, die in den lexikografischen Vergleichen mit anderen Zeichenfolgen verwendet wird, die auf ähnliche Weise aus dem gleichen Gebietsschema konvertiert wurden.|

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="char_type"></a> collate::char_type

Ein Typ, der ein Zeichen vom Typ `CharType` beschreibt.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `CharType` dar.

## <a name="collate"></a> collate::collate

Der Konstruktor für Objekte der collate-Klasse, die als Gebietsschemafacet dient, um Sortierungskonventionen für Zeichenfolgen zu behandeln.

```cpp
public:
    explicit collate(
    size_t _Refs = 0);

protected:
    collate(
const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Parameter

*_Refs*<br/>
Integerwert, der zum Angeben des Speicherverwaltungstyps für das Objekt verwendet wird.

*_Locname*<br/>
Der Name des Gebietsschemas.

### <a name="remarks"></a>Hinweise

Die möglichen Werte für die *_Refs* Parameter und ihre Bedeutung:

- 0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.

- 1: Die Lebensdauer des Objekts muss manuell verwaltet werden.

- \> 1: Diese Werte sind nicht definiert.

Der Konstruktor initialisiert sein Basisobjekt mit **Locale::**[Facet](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="compare"></a> collate::compare

Vergleicht zwei Zeichensequenzen nach ihren facetspezifischen Regeln für Gleichheit oder Ungleichheit.

```cpp
int compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parameter

*first1*<br/>
Zeiger auf das erste Element in der ersten zu vergleichenden Sequenz.

*Last1*<br/>
Zeiger auf das letzte Element in der ersten zu vergleichenden Sequenz.

*first2*<br/>
Zeiger auf das erste Element in der zweiten zu vergleichenden Sequenz.

*Last2*<br/>
Zeiger auf das letzte Element in der zweiten zu vergleichenden Sequenz.

### <a name="return-value"></a>Rückgabewert

Die Memberfunktion gibt Folgendes zurück:

- -1, wenn die erste Sequenz im Vergleich kleiner ist als die zweite Sequenz.

- +1, wenn die zweite Sequenz im Vergleich kleiner ist als die erste Sequenz.

- 0, wenn die Sequenzen gleichwertig sind.

### <a name="remarks"></a>Hinweise

Die erste Sequenz ist im Vergleich kleiner, wenn sie im frühesten ungleichen Paar in den Sequenzen das kleinere Element enthält oder wenn zwar keine ungleichen Paare vorhanden sind, die erste Sequenz aber kürzer ist.

Die Memberfunktion gibt [do_compare](#do_compare)( `first1`, `last1`, `first2`, `last2`) zurück.

### <a name="example"></a>Beispiel

```cpp
// collate_compare.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare ( s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << result2 << endl;
}
```

## <a name="do_compare"></a> collate::do_compare

Eine virtuelle Funktion, die aufgerufen wird, um zwei Zeichensequenzen gemäß ihren facetspezifischen Regeln in Bezug auf Gleichheit oder Ungleichheit zu vergleichen.

```cpp
virtual int do_compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Parameter

*first1*<br/>
Zeiger auf das erste Element in der ersten zu vergleichenden Sequenz.

*Last1*<br/>
Zeiger auf das letzte Element in der ersten zu vergleichenden Sequenz.

*first2*<br/>
Zeiger auf das erste Element in der zweiten zu vergleichenden Sequenz.

*Last2*<br/>
Zeiger auf das letzte Element in der zweiten zu vergleichenden Sequenz.

### <a name="return-value"></a>Rückgabewert

Die Memberfunktion gibt Folgendes zurück:

- -1, wenn die erste Sequenz im Vergleich kleiner ist als die zweite Sequenz.

- +1, wenn die zweite Sequenz im Vergleich kleiner ist als die erste Sequenz.

- 0, wenn die Sequenzen gleichwertig sind.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion vergleicht die Sequenz an [* first1, Last1) * mit der Sequenz an *[first2, last2*). Sie vergleicht Werte durch Anwenden von `operator<` zwischen Paaren entsprechender Elemente des Typs `CharType`. Die erste Sequenz ist im Vergleich kleiner, wenn sie im frühesten ungleichen Paar in den Sequenzen das kleinere Element enthält oder wenn zwar keine ungleichen Paare vorhanden sind, die erste Sequenz aber kürzer ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [collate::compare](#compare), mit dem `do_compare` aufgerufen wird.

## <a name="do_hash"></a> collate::do_hash

Eine virtuelle Funktion, die aufgerufen wird, um den Hashwert der Sequenzen anhand der facetspezifischen Regeln zu bestimmen.

```cpp
virtual long do_hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Ein Zeiger auf das erste Zeichen in der Sequenz, dessen Hashwert bestimmt werden soll.

*last*<br/>
Ein Zeiger auf das letzte Zeichen in der Sequenz, dessen Hashwert bestimmt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Hashwert des Typs **long** für die Sequenz.

### <a name="remarks"></a>Hinweise

Ein Hashwert kann beispielsweise nützlich sein, um Sequenzen pseudozufällig auf ein Array von Listen zu verteilen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [hash](#hash), mit dem `do_hash` aufgerufen wird.

## <a name="do_transform"></a> collate::do_transform

Eine virtuelle Funktion, die aufgerufen wird, um eine Zeichenfolge aus einem Gebietsschema in eine Zeichenfolge zu konvertieren, die in den lexikografischen Vergleichen mit anderen Zeichensequenzen verwendet werden kann, die auf ähnliche Weise aus demselben Gebietsschema konvertiert wurden.

```cpp
virtual string_type do_transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Ein Zeiger auf das erste Zeichen in der zu konvertierenden Sequenz.

*last*<br/>
Ein Zeiger auf das letzte Zeichen in der zu konvertierenden Sequenz.

### <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge, bei der es sich um die transformierte Zeichensequenz handelt.

### <a name="remarks"></a>Hinweise

Die geschützte virtuelle Memberfunktion gibt ein Objekt der Klasse [string_type](#string_type) zurück, dessen gesteuerte Sequenz eine Kopie der Sequenz [ `first`, `last`) ist. Wenn eine von collate\< **CharType**> abgeleitete Klasse [do_compare](#do_compare) überschreibt, sollte sie für die Übereinstimmung auch `do_transform` überschreiben. Bei der Übergabe an `collate::compare` müssen zwei transformierte Zeichenfolgen zu demselben Ergebnis führen, das Sie erhalten würden, wenn die untransformierten Zeichenfolgen für den Vergleich in der abgeleiteten Klasse übergeben würden.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [transform](#transform), mit dem `do_transform` aufgerufen wird.

## <a name="hash"></a> collate::hash

Bestimmt den Hashwert der Sequenz nach ihren facetspezifischen Regeln.

```cpp
long hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Ein Zeiger auf das erste Zeichen in der Sequenz, dessen Hashwert bestimmt werden soll.

*last*<br/>
Ein Zeiger auf das letzte Zeichen in der Sequenz, dessen Hashwert bestimmt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Hashwert des Typs **long** für die Sequenz.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [do_hash](#do_hash)( `first`, `last`) zurück.

Ein Hashwert kann beispielsweise nützlich sein, um Sequenzen pseudozufällig auf ein Array von Listen zu verteilen.

### <a name="example"></a>Beispiel

```cpp
// collate_hash.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("\x00dfzz abc."); // \x00df is the German sharp-s (looks like beta), it comes before z in the alphabet
   _TCHAR * s2 = _T("zzz abc."); // \x00df is the German sharp-s (looks like beta), it comes before z in the alphabet

   long r1 = use_facet< collate<_TCHAR> > ( loc ).
      hash (s1, &s1[_tcslen( s1 )-1 ]);
   long r2 =  use_facet< collate<_TCHAR> > ( loc ).
      hash (s2, &s2[_tcslen( s2 )-1 ] );
   cout << r1 << " " << r2 << endl;
}
```

```Output
541187293 551279837
```

## <a name="string_type"></a> collate::string_type

Ein Typ, der eine Zeichenfolge vom Typ `basic_string` beschreibt, die Zeichen vom Typ `CharType` enthält.

```cpp
typedef basic_string<CharType> string_type;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [basic_string](../standard-library/basic-string-class.md), deren Objekte Kopien der Quellsequenz speichern können.

### <a name="example"></a>Beispiel

Unter [transform](#transform) finden Sie ein Beispiel für das Deklarieren und Verwenden von `string_type`.

## <a name="transform"></a> collate::transform

Konvertiert eine Zeichenfolge von einem Gebietsschema in eine Zeichenfolge, die in den lexikografischen Vergleichen mit anderen Zeichenfolgen verwendet wird, die auf ähnliche Weise aus dem gleichen Gebietsschema konvertiert wurden.

```cpp
string_type transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Ein Zeiger auf das erste Zeichen in der zu konvertierenden Sequenz.

*last*<br/>
Ein Zeiger auf das letzte Zeichen in der zu konvertierenden Sequenz.

### <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge, die die transformierte Zeichensequenz enthält.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [Do_transform](#do_transform)(`first`, `last`).

### <a name="example"></a>Beispiel

```cpp
// collate_transform.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   _TCHAR* s1 = _T("\x00dfzz abc.");
   // \x00df is the German sharp-s (looks like beta),
   // it comes before z in the alphabet
   _TCHAR* s2 = _T("zzz abc.");

   collate<_TCHAR>::string_type r1;   // OK for typedef
   r1 = use_facet< collate<_TCHAR> > ( loc ).
      transform (s1, &s1[_tcslen( s1 )-1 ]);

   cout << r1 << endl;

   basic_string<_TCHAR> r2 = use_facet< collate<_TCHAR> > ( loc ).
      transform (s2, &s2[_tcslen( s2 )-1 ]);

   cout << r2 << endl;

   int result1 = use_facet<collate<_TCHAR> > ( loc ).compare
      (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );

   cout << _tcscmp(r1.c_str( ),r2.c_str( )) << result1
      << _tcscmp(s1,s2) <<endl;
}
```

```Output

-1-11
```

## <a name="see-also"></a>Siehe auch

[\<locale>](../standard-library/locale.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
