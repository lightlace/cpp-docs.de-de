---
title: '&lt;ostream&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 094952a76d8e46e4244cf57a8c5a47c929f3ae37
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960351"
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
