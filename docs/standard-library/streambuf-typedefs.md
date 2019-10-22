---
title: '&lt;streambuf&gt;-Typdefinition'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 1c9850ad7d7ec9b9c3554e6806f4790ef3613b08
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688936"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt;-Typdefinition

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a> streambuf

Eine Spezialisierung von `basic_streambuf`, die **char** als Vorlagen Parameter verwendet.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Klassen Vorlage [basic_streambuf](../standard-library/basic-streambuf-class.md), die auf Elemente des Typs **char** mit Standard Zeichen Merkmalen spezialisiert ist.

## <a name="wstreambuf"></a> wstreambuf

Eine Spezialisierung von `basic_streambuf`, die **wchar_t** als Vorlagen Parameter verwendet.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Klassen Vorlage [basic_streambuf](../standard-library/basic-streambuf-class.md), die auf Elemente vom Typ **wchar_t** mit Standard Zeichen Merkmalen spezialisiert ist.

## <a name="see-also"></a>Siehe auch

[\<streambuf>](../standard-library/streambuf.md)
