---
title: char_traits&lt;wchar_t&gt;-Struktur
ms.date: 11/04/2016
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
ms.openlocfilehash: ef40a34b5aa874c8bdf48aeb7657ae3496160eec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584742"
---
# <a name="chartraitsltwchartgt-struct"></a>char_traits&lt;wchar_t&gt;-Struktur

Eine Klasse, die eine Spezialisierung der Vorlagenstruktur **Char_traits\<CharType >** auf ein Element vom Typ **"wchar_t"**.

## <a name="syntax"></a>Syntax

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>Hinweise

Dank der Spezialisierung kann die Struktur Bibliotheksfunktionen nutzen, die Objekte dieses Typs zu bearbeiten **"wchar_t"**.

## <a name="requirements"></a>Anforderungen

**Header:** \<string>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[char_traits-Struktur](../standard-library/char-traits-struct.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
