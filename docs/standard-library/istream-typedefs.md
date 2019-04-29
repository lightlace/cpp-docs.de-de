---
title: '&lt;iStream&gt;-Typedefs'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: f647fba2036f6c69cb02393e30553c66df34b9dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413293"
---
# <a name="ltistreamgt-typedefs"></a>&lt;iStream&gt;-Typedefs

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a> iostream

Ein Typ `basic_iostream` auf **Char**.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_iostream](../standard-library/basic-iostream-class.md), die auf Elemente des Typs **Char** mit Standard-Zeichenmerkmale.

## <a name="istream"></a> istream

Ein Typ `basic_istream` auf **Char**.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_istream](../standard-library/basic-istream-class.md), die auf Elemente des Typs **Char** mit Standard-Zeichenmerkmale.

## <a name="wiostream"></a> wiostream

Ein Typ `basic_iostream` auf **"wchar_t"**.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_iostream](../standard-library/basic-iostream-class.md), die auf Elemente des Typs **"wchar_t"** mit Standard-Zeichenmerkmale.

## <a name="wistream"></a> wistream

Ein Typ `basic_istream` auf **"wchar_t"**.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_istream](../standard-library/basic-istream-class.md), die auf Elemente des Typs **"wchar_t"** mit Standard-Zeichenmerkmale.

## <a name="see-also"></a>Siehe auch

[\<istream>](../standard-library/istream.md)<br/>
