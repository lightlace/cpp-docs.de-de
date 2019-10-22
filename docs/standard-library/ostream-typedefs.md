---
title: '&lt;ostream&gt;-Typdefinitionen'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: d0ceae12069712c7a124990d0f81968c21bc683a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687232"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt;-Typdefinitionen

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a> ostream

Erstellt einen Typ aus Basic_ostream, der auf **char** und `char_traits` spezialisiert ist, der auf **char**spezialisiert ist.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Klassen Vorlage [basic_ostream](../standard-library/basic-ostream-class.md), die auf Elemente des Typs **char** mit Standard Zeichen Merkmalen spezialisiert ist.

## <a name="wostream"></a> wostream

Erstellt einen Typ aus Basic_ostream, der auf **wchar_t** spezialisiert ist, und `char_traits` spezialisiert auf **wchar_t**.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Klassen Vorlage [basic_ostream](../standard-library/basic-ostream-class.md), die auf Elemente vom Typ **wchar_t** mit Standard Zeichen Merkmalen spezialisiert ist.

## <a name="see-also"></a>Siehe auch

[\<ostream>](../standard-library/ostream.md)
