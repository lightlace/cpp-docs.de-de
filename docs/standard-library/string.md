---
title: '&lt;string&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- string/std::<string>
- <string>
dev_langs:
- C++
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e341b15baa54b57148582c92beb9d231da8c96bb
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954570"
---
# <a name="ltstringgt"></a>&lt;string&gt;

Definiert die Containervorlagenklasse `basic_string` und verschiedene unterstützende Vorlagen.

Weitere Informationen zu `basic_string` finden Sie unter [basic_string-Klasse](../standard-library/basic-string-class.md).

## <a name="syntax"></a>Syntax

```cpp
#include <string>
```

## <a name="remarks"></a>Hinweise

Die Programmiersprache C++ und die C++-Standardbibliothek unterstützen zwei Arten von Zeichenfolgen:

- Auf NULL endende Zeichenarrays werden häufig als C-Zeichenfolgen bezeichnet.

- Vorlagenklassenobjekte des Typs `basic_string`, verarbeiten alle **Char**--ähnlichen Vorlagenargumente.

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|Ein Typ, der eine Spezialisierung der Vorlagenklasse beschreibt `basic_string` mit Elementen des Typs **Char** als eine `string`.|
|[wstring](../standard-library/string-typedefs.md#wstring)|Ein Typ, der eine Spezialisierung der Vorlagenklasse beschreibt `basic_string` mit Elementen des Typs **"wchar_t"** als eine `wstring`.|
|[u16string](../standard-library/string-typedefs.md#u16string)|Ein Typ, der eine Spezialisierung der Vorlagenklasse `basic_string` basierend auf Elementen des Typs `char16_t` beschreibt.|
|[u32string](../standard-library/string-typedefs.md#u32string)|Ein Typ, der eine Spezialisierung der Vorlagenklasse `basic_string` basierend auf Elementen des Typs `char32_t` beschreibt.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator+](../standard-library/string-operators.md#op_add)|Verkettet zwei Zeichenfolgenobjekte.|
|[operator!=](../standard-library/string-operators.md#op_neq)|Testet, ob das Zeichenfolgenobjekt links vom Operator ungleich dem Zeichenfolgenobjekt rechts vom Operator ist.|
|[operator==](../standard-library/string-operators.md#op_eq_eq)|Testet, ob das Zeichenfolgenobjekt links vom Operator gleich dem Zeichenfolgenobjekt rechts vom Operator ist.|
|[operator<](../standard-library/string-operators.md#op_lt)|Testet, ob das Zeichenfolgenobjekt links vom Operator kleiner als das Zeichenfolgenobjekt rechts vom Operator ist.|
|[operator<=](../standard-library/string-operators.md#op_lt_eq)|Testet, ob das Zeichenfolgenobjekt links vom Operator kleiner als oder gleich dem Zeichenfolgenobjekt rechts vom Operator ist.|
|[operator<\<](../standard-library/string-operators.md#op_lt_lt)|Eine Vorlagenfunktion, die eine Zeichenfolge in den Ausgabestream einfügt.|
|[operator>](../standard-library/string-operators.md#op_gt)|Testet, ob das Zeichenfolgenobjekt links vom Operator größer als das Zeichenfolgenobjekt rechts vom Operator ist.|
|[operator>=](../standard-library/string-operators.md#op_gt_eq)|Testet, ob das Zeichenfolgenobjekt links vom Operator größer als oder gleich dem Zeichenfolgenobjekt rechts vom Operator ist.|
|[operator>>](../standard-library/string-operators.md#op_gt_gt)|Eine Vorlagenfunktion, die eine Zeichenfolge aus dem Eingabestream extrahiert.|

### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen

|||
|-|-|
|[swap](../standard-library/string-functions.md#swap)|Tauscht die Arrays von Zeichen für zwei Zeichenfolgen aus.|
|[stod](../standard-library/string-functions.md#stod)|Konvertiert eine Zeichenfolge in eine **doppelte**.|
|[stof](../standard-library/string-functions.md#stof)|Konvertiert eine Zeichenfolge in eine **"float"**.|
|[stoi](../standard-library/string-functions.md#stoi)|Konvertiert eine Zeichenfolge in eine Ganzzahl.|
|[stold](../standard-library/string-functions.md#stold)|Konvertiert eine Zeichenfolge in eine **long double**.|
|[stoll](../standard-library/string-functions.md#stoll)|Konvertiert eine Zeichenfolge in eine **long long**.|
|[stoul](../standard-library/string-functions.md#stoul)|Konvertiert eine Zeichenfolge in eine **unsigned long**.|
|[stoull](../standard-library/string-functions.md#stoull)|Konvertiert eine Zeichenfolge in eine **long long ohne Vorzeichen**.|
|[to_string](../standard-library/string-functions.md#to_string)|Konvertiert einen Wert in einen `string`-Wert.|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|Konvertiert einen Wert in eine breite `string`.|

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[GetLine-Vorlage](../standard-library/string-functions.md#getline)|Extrahiert Zeichenfolgen aus dem Eingabestream zeilenweise.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_string-Klasse](../standard-library/basic-string-class.md)|Eine Vorlagenklasse, die Objekte beschreibt, die eine Sequenz von beliebigen zeichenartigen Objekten speichern können.|
|[char_traits-Struktur](../standard-library/char-traits-struct.md)|Eine Vorlagenklasse, die Attribute beschreibt, die mit einem Zeichen des Typs "CharType" zugeordnet sind.|

### <a name="specializations"></a>Spezialisierungen

|||
|-|-|
|[char_traits\<char>-Structur](../standard-library/char-traits-char-struct.md)|Eine Struktur, die eine Spezialisierung der Vorlagenstruktur `char_traits`\<CharType> für ein Element des Typs `char` ist.|
|[char_traits<wchar_t>-Struktur](../standard-library/char-traits-wchar-t-struct.md)|Eine Struktur, die eine Spezialisierung der Vorlagenstruktur `char_traits`\<CharType> für ein Element des Typs `wchar_t` ist.|
|[char_traits<char16_t>-Struktur](../standard-library/char-traits-char16-t-struct.md)|Eine Struktur, die eine Spezialisierung der Vorlagenstruktur `char_traits`\<CharType> für ein Element des Typs `char16_t` ist.|
|[char_traits<char32_t>-Struktur](../standard-library/char-traits-char32-t-struct.md)|Eine Struktur, die eine Spezialisierung der Vorlagenstruktur `char_traits`\<CharType> für ein Element des Typs `char32_t` ist.|

## <a name="requirements"></a>Anforderungen

- **Header:** \<string>

- **Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
