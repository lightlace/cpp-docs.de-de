---
title: '&lt;streambuf&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 81c7cd875c6083ee77701116f6b1179760373ec0
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953991"
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
