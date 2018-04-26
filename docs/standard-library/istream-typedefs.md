---
title: '&lt;istream&gt;-Typedefs | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: 0c27a5fcb3efab861b2f7da4ea4a5fdf978bbbb1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltistreamgt-typedefs"></a>&lt;iStream&gt;-Typedefs

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a> iostream

Ein `basic_iostream`-Typ, der auf `char` spezialisiert ist.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [basic_iostream](../standard-library/basic-iostream-class.md), die auf Elemente des Typs `char` mit Standardzeichenmerkmalen spezialisiert ist.

## <a name="istream"></a> istream

Ein `basic_istream`-Typ, der auf `char` spezialisiert ist.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [basic_istream](../standard-library/basic-istream-class.md), die auf Elemente des Typs `char` mit Standardzeichenmerkmalen spezialisiert ist.

## <a name="wiostream"></a> wiostream

Ein `basic_iostream`-Typ, der auf `wchar_t` spezialisiert ist.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [basic_iostream](../standard-library/basic-iostream-class.md), die auf Elemente des Typs `wchar_t` mit Standardzeichenmerkmalen spezialisiert ist.

## <a name="wistream"></a> wistream

Ein `basic_istream`-Typ, der auf `wchar_t` spezialisiert ist.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [basic_istream](../standard-library/basic-istream-class.md), die auf Elemente des Typs `wchar_t` mit Standardzeichenmerkmalen spezialisiert ist.

## <a name="see-also"></a>Siehe auch

[\<istream>](../standard-library/istream.md)<br/>
