---
title: '&lt;string&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
caps.latest.revision: 12
manager: ghogen
ms.openlocfilehash: c485457b5fefb1b95e5fe0304ec897aef16d9fbe
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltstringgt-typedefs"></a>&lt;string&gt;-Typdefinitionen

||||
|-|-|-|
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|
|[wstring](#wstring)|

## <a name="string"></a> string

Ein Typ, der eine Spezialisierung der Vorlagenklasse [Basic_string](../standard-library/basic-string-class.md) mit Elementen des Typs`char` beschreibt.

Andere `basic_string` spezialisierende Typdefinitionen umfassen [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string) und [u32string](../standard-library/string-typedefs.md#u32string).

```cpp
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```

### <a name="remarks"></a>Hinweise

Die folgenden Deklarationen sind gleichwertig:

```cpp
string str("");

basic_string<char> str("");
```

Eine Liste der String-Konstruktoren finden Sie unter [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string"></a> u16string

Ein Typ, der eine Spezialisierung der Vorlagenklasse [basic_string](../standard-library/basic-string-class.md) mit Elementen des Typs `char16_t` beschreibt.

Andere `basic_string` spezialisierende Typdefinitionen umfassen [wstring](../standard-library/string-typedefs.md#wstring), [string](../standard-library/string-typedefs.md#string) und [u32string](../standard-library/string-typedefs.md#u32string).

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>Hinweise

Eine Liste der String-Konstruktoren finden Sie unter [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string"></a> u32string

Ein Typ, der eine Spezialisierung der Vorlagenklasse [Basic_string](../standard-library/basic-string-class.md) mit Elementen des Typs`char32_t` beschreibt.

Andere `basic_string` spezialisierende Typdefinitionen umfassen [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) und [wstring](../standard-library/string-typedefs.md#wstring).

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>Hinweise

Eine Liste der String-Konstruktoren finden Sie unter [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring"></a> wstring

Ein Typ, der eine Spezialisierung der Vorlagenklasse [Basic_string](../standard-library/basic-string-class.md) mit Elementen des Typs`wchar_t` beschreibt.

Andere `basic_string` spezialisierende Typdefinitionen umfassen [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) und [u32string](../standard-library/string-typedefs.md#u32string).

```cpp
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```

### <a name="remarks"></a>Hinweise

Die folgenden Deklarationen sind gleichwertig:

```cpp
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```

Eine Liste der String-Konstruktoren finden Sie unter [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> Die Größe von `wchar_t` hängt von der Implementierung ab. Wenn Ihr Code von `wchar_t` abhängig ist, um eine bestimmte Größe aufzuweisen, überprüfen Sie die Implementierung der Plattform (z. B. mit `sizeof(wchar_t)`). Wenn Sie einen Zeichenfolgentyp mit einer Breite benötigen, die auf allen Plattformen garantiert dieselbe ist, verwenden Sie [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) oder [u32string](../standard-library/string-typedefs.md#u32string).

## <a name="see-also"></a>Siehe auch

[\<string>](../standard-library/string.md)<br/>
