---
title: '&lt;istream&gt;-Typedefs | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: bea06c9799783feafaff1f68f4019463e452a4f2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958854"
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
