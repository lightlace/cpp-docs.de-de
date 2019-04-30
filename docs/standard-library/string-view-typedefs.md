---
title: '&lt;String_view&gt; Typedefs'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 16d7ba49facf24dcffb7df444e445d83d92255e0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346968"
---
# <a name="ltstringviewgt-typedefs"></a>&lt;String_view&gt; Typedefs

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a> string_view

Ein Typ, eine Spezialisierung der Klassenvorlage beschreibt [Basic_string_view](../standard-library/basic-string-view-class.md) mit Elementen des Typs **Char**.

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>Hinweise

Die folgenden Deklarationen sind gleichwertig:

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

Eine Liste der String-Konstruktoren finden Sie unter [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u16string_view"></a> u16string_view

Ein Typ, eine Spezialisierung der Klassenvorlage beschreibt [Basic_string_view](../standard-library/basic-string-view-class.md) mit Elementen des Typs `char16_t`.

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Hinweise

Eine Liste der String-Konstruktoren finden Sie unter [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="u32string_view"></a> u32string_view

Ein Typ, eine Spezialisierung der Klassenvorlage beschreibt [Basic_string_view](../standard-library/basic-string-view-class.md) mit Elementen des Typs `char32_t`.

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Hinweise

Eine Liste der String-Konstruktoren finden Sie unter [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

## <a name="wstring_view"></a>  wstring_view

Ein Typ, eine Spezialisierung der Klassenvorlage beschreibt [Basic_string_view](../standard-library/basic-string-view-class.md) mit Elementen des Typs **"wchar_t"**.

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>Hinweise

Die folgenden Deklarationen sind gleichwertig:

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

Eine Liste der String-Konstruktoren finden Sie unter [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string).

> [!NOTE]
> Die Größe des **"wchar_t"** beträgt zwei Bytes auf Windows, aber dies ist nicht unbedingt der Fall für alle Plattformen. Wenn Sie einen String_view Breitzeichen benötigen mit einer Breite, die dieselbe auf allen Plattformen garantiert ist, verwenden Sie [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) oder [u32string_view](../standard-library/string-view-typedefs.md#u32string_view).

## <a name="see-also"></a>Siehe auch

[\<string_view>](../standard-library/string-view.md)<br/>
