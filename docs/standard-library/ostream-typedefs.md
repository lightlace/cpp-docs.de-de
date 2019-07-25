---
title: '&lt;ostream&gt;-Typdefinitionen'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 18f30a12a6f4d2b97cb5dca3ace98e6241d856a7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447162"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt;-Typdefinitionen

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a> ostream

Erstellt einen Typ aus Basic_ostream, der auf **char** spezialisiert und `char_traits` auf **char**spezialisiert ist.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagen Klasse [basic_ostream](../standard-library/basic-ostream-class.md), die auf Elemente des Typs **char** mit Standard Zeichen Merkmalen spezialisiert ist.

## <a name="wostream"></a> wostream

Erstellt einen Typ aus Basic_ostream, der auf **wchar_t** spezialisiert ist `char_traits` und auf **wchar_t**spezialisiert ist.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagen Klasse [basic_ostream](../standard-library/basic-ostream-class.md), die auf Elemente vom Typ **wchar_t** mit Standard Zeichen Merkmalen spezialisiert ist.

## <a name="see-also"></a>Siehe auch

[\<ostream>](../standard-library/ostream.md)
