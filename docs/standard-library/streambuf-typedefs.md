---
title: '&lt;streambuf&gt;-Typdefinition'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 505739861771a05dd39741f432579a6e9b2d0c26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412383"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt;-Typdefinition

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a> streambuf

Eine Spezialisierung der `basic_streambuf` verwendet **Char** als Vorlagenparameter.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse ["basic_streambuf"](../standard-library/basic-streambuf-class.md), die auf Elemente des Typs **Char** mit Standard-Zeichenmerkmale.

## <a name="wstreambuf"></a> wstreambuf

Eine Spezialisierung der `basic_streambuf` verwendet **"wchar_t"** als Vorlagenparameter.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse ["basic_streambuf"](../standard-library/basic-streambuf-class.md), die auf Elemente des Typs **"wchar_t"** mit Standard-Zeichenmerkmale.

## <a name="see-also"></a>Siehe auch

[\<streambuf>](../standard-library/streambuf.md)<br/>
