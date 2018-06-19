---
title: '&lt;streambuf&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 8fb1713dfbc2d9766c488f21d324d801a4886d68
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854216"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt;-Typdefinition

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a> streambuf

Eine Spezialisierung von `basic_streambuf`, die `char` als Vorlagenparameter verwendet.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [basic_filebuf](../standard-library/basic-streambuf-class.md), die auf Elemente vom Typ `char` mit Standardzeichenmerkmalen spezialisiert ist.

## <a name="wstreambuf"></a> wstreambuf

Eine Spezialisierung von `basic_streambuf`, die `wchar_t` als Vorlagenparameter verwendet.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [basic_filebuf](../standard-library/basic-streambuf-class.md), die auf Elemente vom Typ `wchar_t` mit Standardzeichenmerkmalen spezialisiert ist.

## <a name="see-also"></a>Siehe auch

[\<streambuf>](../standard-library/streambuf.md)<br/>
