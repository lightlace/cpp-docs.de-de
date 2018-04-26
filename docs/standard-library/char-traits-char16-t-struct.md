---
title: char_traits&lt;char16_t&gt;-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b76839dee5df211331f10f11e20ab9a45a2f4eeb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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
