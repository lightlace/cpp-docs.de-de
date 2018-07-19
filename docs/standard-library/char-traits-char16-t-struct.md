---
title: char_traits&lt;char16_t&gt;-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24d6c3d5dd11290ce4151b5d54885ba492b8ee45
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845283"
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

[\<string>](../standard-library/string.md)<br/>
[char_traits-Struktur](../standard-library/char-traits-struct.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
