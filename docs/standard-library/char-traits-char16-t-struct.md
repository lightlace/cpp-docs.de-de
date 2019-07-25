---
title: char_traits&lt;char16_t&gt;-Struktur
ms.date: 11/04/2016
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
ms.openlocfilehash: d83f5278c2c4f8344334bfce40946612e9ca3e56
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448967"
---
# <a name="chartraitsltchar16tgt-struct"></a>char_traits&lt;char16_t&gt;-Struktur

Eine Struktur, die eine Spezialisierung der Vorlagenstruktur **char_traits\<CharType>** für ein Element des Typs `char16_t` ist.

## <a name="syntax"></a>Syntax

```cpp
template <>
struct char_traits<char16_t>;
```

## <a name="remarks"></a>Hinweise

Dank der Spezialisierung kann die Struktur Bibliotheksfunktionen nutzen, die Objekte des Typs `char16_t` bearbeiten.

## <a name="requirements"></a>Anforderungen

**Header:** \<string>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<string>](../standard-library/string.md)\
[char_traits-Struktur](../standard-library/char-traits-struct.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
