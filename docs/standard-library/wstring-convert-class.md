---
title: wstring_convert-Klasse
ms.date: 11/04/2016
f1_keywords:
- wstring/stdext::cvt::wstring_convert
- locale/std::wstring_convert::byte_string
- locale/std::wstring_convert::wide_string
- locale/std::wstring_convert::state_type
- locale/std::wstring_convert::int_type
- locale/std::wstring_convert::from_bytes
- locale/std::wstring_convert::to_bytes
- locale/std::wstring_convert::converted
- locale/std::wstring_convert::state
helpviewer_keywords:
- stdext::cvt [C++], wstring_convert
- std::wstring_convert [C++], byte_string
- std::wstring_convert [C++], wide_string
- std::wstring_convert [C++], state_type
- std::wstring_convert [C++], int_type
- std::wstring_convert [C++], from_bytes
- std::wstring_convert [C++], to_bytes
- std::wstring_convert [C++], converted
- std::wstring_convert [C++], state
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
ms.openlocfilehash: df3b003289dcd86e8033521d8cb0cacdbb7dfbd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636955"
---
# <a name="wstringconvert-class"></a>wstring_convert-Klasse

Die Vorlagenklasse `wstring_convert` führt Konvertierungen zwischen einer breiten Zeichenfolge und einer Bytezeichenfolge durch.

## <a name="syntax"></a>Syntax

```cpp
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```

### <a name="parameters"></a>Parameter

*codecvt*<br/>
Das Facet [locale](../standard-library/locale-class.md), das das Konvertierungsobjekt darstellt.

*Elem*<br/>
Der Breitzeichen-Elementtyp.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt, das Konvertierungen zwischen breiten Zeichenfolgenobjekten der Klasse `std::basic_string<Elem>` und Bytezeichenfolgenobjekten der `std::basic_string<char>` (auch bekannt als `std::string`) steuert. Die Vorlagenklasse definiert die Typen `wide_string` und `byte_string` als Synonyme für diese beiden Typen. Konvertierung zwischen einer Sequenz von `Elem`-Werten (in einem `wide_string`-Objekt gespeichert) und Multibytesequenzen (in einem `byte_string`-Objekt gespeichert) erfolgt durch ein Objekt der Klasse `Codecvt<Elem, char, std::mbstate_t>`, das die Anforderungen des Facets `std::codecvt<Elem, char, std::mbstate_t>` für die Standardcodekonvertierung erfüllt.

Ein Objekt dieser Vorlagenklasse speichert:

- Eine bei Fehlern anzuzeigende Bytezeichenfolge

- Eine bei Fehlern anzuzeigende breite Zeichenfolge

- Ein Zeiger auf das zugeordnete Konvertierungsobjekt (das freigegeben wird, wenn das wbuffer_convert-Objekt zerstört wird)

- Ein Konvertierungsstatusobjekt vom Typ [state_type](#state_type)

- Eine Konvertierungsanzahl

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[wstring_convert](#wstring_convert)|Konstruiert ein Objekt vom Typ `wstring_convert`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[byte_string](#byte_string)|Ein Typ, der eine Bytezeichenfolge darstellt.|
|[wide_string](#wide_string)|Ein Typ, der eine breite Zeichenfolge darstellt.|
|[state_type](#state_type)|Ein Typ, der den Konvertierungszustand darstellt.|
|[int_type](#int_type)|Ein Typ, der eine ganze Zahl darstellt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[from_bytes](#from_bytes)|Konvertiert eine Bytezeichenfolge in eine breite Zeichenfolge.|
|[to_bytes](#to_bytes)|Konvertiert eine breite Zeichenfolge in eine Bytezeichenfolge.|
|[converted](#converted)|Gibt die Anzahl der erfolgreichen Konvertierungen zurück.|
|[state](#state)|Gibt ein Objekt zurück, das den Zustand für die Konvertierung darstellt.|

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="byte_string"></a> wstring_convert::byte_string

Ein Typ, der eine Bytezeichenfolge darstellt.

```cpp
typedef std::basic_string<char> byte_string;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `std::basic_string<char>`.

## <a name="converted"></a> wstring_convert::converted

Gibt die Anzahl der erfolgreichen Konvertierungen zurück.

```cpp
size_t converted() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der erfolgreichen Konvertierungen.

### <a name="remarks"></a>Hinweise

Die Anzahl der erfolgreichen Konvertierungen wird im Konvertierungsanzahlobjekt gespeichert.

## <a name="from_bytes"></a> wstring_convert::from_bytes

Konvertiert eine Bytezeichenfolge in eine breite Zeichenfolge.

```cpp
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Byte*|Die zu konvertierende Einzelelement-Bytesequenz.|
|*ptr*|Die auf NULL endende Zeichenfolge im C-Stil der zu konvertierenden Zeichen.|
|*BSTR*|Der zu konvertierende [byte_string](#byte_string).|
|*Erste*|Das erste Zeichen in einem Bereich von zu konvertierenden Zeichen.|
|*last*|Das letzte Zeichen in einem Bereich von zu konvertierenden Zeichen.|

### <a name="return-value"></a>Rückgabewert

Ein breites Zeichenfolgenobjekt, das sich aus der Konvertierung ergibt.

### <a name="remarks"></a>Hinweise

Wenn die [konvertierungszustand](../standard-library/wstring-convert-class.md) Objekt war *nicht* mit einem expliziten Wert erstellt, es auf seinen Standardwert (den ursprünglichen konvertierungszustand) festgelegt ist vor Beginn der Konvertierung. Andernfalls bleibt es unverändert.

Die Anzahl der erfolgreich konvertierten Eingabeelemente wird im Konvertierungsanzahlobjekt gespeichert. Wenn kein Konvertierungsfehler auftritt, gibt die Memberfunktion die konvertierte breite Zeichenfolge zurück. Wenn das Objekt mit einem Initialisierer für die Breitzeichen-Fehlermeldung erstellt wurde, gibt die Memberfunktion das Breitzeichen-Fehlermeldungsobjekt zurück. Andernfalls gibt die Memberfunktion ein Objekt der Klasse [range_error](../standard-library/range-error-class.md) aus.

## <a name="int_type"></a> wstring_convert::int_type

Ein Typ, der eine ganze Zahl darstellt.

```cpp
typedef typename wide_string::traits_type::int_type int_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `wide_string::traits_type::int_type`.

## <a name="state"></a> wstring_convert::state

Gibt ein Objekt zurück, das den Zustand für die Konvertierung darstellt.

```cpp
state_type state() const;
```

### <a name="return-value"></a>Rückgabewert

Das [Konvertierungsstatusobjekt](../standard-library/wstring-convert-class.md), das den Status der Konvertierung darstellt.

### <a name="remarks"></a>Hinweise

## <a name="state_type"></a> wstring_convert::state_type

Ein Typ, der den Konvertierungszustand darstellt.

```cpp
typedef typename Codecvt::state_type state_type;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt ein Objekt, das einen Konvertierungszustand repräsentieren kann. Der Typ ist ein Synonym für `Codecvt::state_type`.

## <a name="to_bytes"></a> wstring_convert::to_bytes

Konvertiert eine breite Zeichenfolge in eine Bytezeichenfolge.

```cpp
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Char*|Die zu konvertierenden Breitzeichenfolgen.|
|*Wptr*|Die auf NULL endende Sequenz im C-Stil, die bei `wptr`beginnt und konvertiert werden soll.|
|*WSTR*|Die zu konvertierende Zeichenfolge vom Typ [wide_string](#wide_string).|
|*Erste*|Das erste Element in dem zu konvertierenden Elementbereich.|
|*last*|Das letzte Element in dem zu konvertierenden Elementbereich.|

### <a name="remarks"></a>Hinweise

Wenn die [konvertierungszustand](../standard-library/wstring-convert-class.md) Objekt war *nicht* mit einem expliziten Wert erstellt, es auf seinen Standardwert (den ursprünglichen konvertierungszustand) festgelegt ist vor Beginn der Konvertierung. Andernfalls bleibt es unverändert.

Die Anzahl der erfolgreich konvertierten Eingabeelemente wird im Konvertierungsanzahlobjekt gespeichert. Wenn kein Konvertierungsfehler auftritt, gibt die Memberfunktion die konvertierte Bytezeichenfolge zurück. Wenn das Objekt mit einem Initialisierer für die Bytezeichen-Fehlermeldung erstellt wurde, gibt die Memberfunktion das Bytezeichen-Fehlermeldungsobjekt zurück. Andernfalls gibt die Memberfunktion ein Objekt der Klasse [range_error](../standard-library/range-error-class.md) aus.

## <a name="wide_string"></a> wstring_convert::wide_string

Ein Typ, der eine breite Zeichenfolge darstellt.

```cpp
typedef std::basic_string<Elem> wide_string;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `std::basic_string<Elem>`.

## <a name="wstring_convert"></a> wstring_convert::wstring_convert

Konstruiert ein Objekt vom Typ `wstring_convert`.

```cpp
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*\*Pcvt*|Das Objekt des `Codecvt`-Typs zum Durchführen der Konvertierung.|
|*_State*|Das Objekt vom Typ [state_type](#state_type), das den Konvertierungsstatus darstellt.|
|*_Berr*|Die bei Fehlern anzuzeigende [byte_string](#byte_string).|
|*Werr*|Die bei Fehlern anzuzeigende [wide_string](#wide_string).|

### <a name="remarks"></a>Hinweise

Der erste Konstruktor speichert *Pcvt_arg* im [Konvertierungsobjekt](../standard-library/wstring-convert-class.md).
