---
title: '&lt;ostream&gt;-Typdefinitionen'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 02936fdfc990ea65a99b2875cf7f482eb2ce4ebe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370872"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt;-Typdefinitionen

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a> ostream

Erstellt einen Typ aus Basic_ostream, der auf spezialisierte ist **Char** und `char_traits` auf **Char**.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_ostream](../standard-library/basic-ostream-class.md), die auf Elemente des Typs **Char** mit Standard-Zeichenmerkmale.

## <a name="wostream"></a> wostream

Erstellt einen Typ aus Basic_ostream, der auf spezialisierte ist **"wchar_t"** und `char_traits` auf **"wchar_t"**.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_ostream](../standard-library/basic-ostream-class.md), die auf Elemente des Typs **"wchar_t"** mit Standard-Zeichenmerkmale.

## <a name="see-also"></a>Siehe auch

[\<ostream>](../standard-library/ostream.md)<br/>
