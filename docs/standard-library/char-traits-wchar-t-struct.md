---
title: char_traits&lt;wchar_t&gt;-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2b20b72bf92679395b19b2ad6b8ae68143bb6d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="chartraitsltwchartgt-struct"></a>char_traits&lt;wchar_t&gt;-Struktur

Eine Klasse, die eine Spezialisierung der Vorlagenstruktur **char_traits\<CharType>** für ein Element des Typs `wchar_t` ist.

## <a name="syntax"></a>Syntax

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>Hinweise

Dank der Spezialisierung kann die Struktur Bibliotheksfunktionen nutzen, die Objekte dieses Typs `wchar_t` bearbeiten.

## <a name="requirements"></a>Anforderungen

**Header:** \<string>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[char_traits-Struktur](../standard-library/char-traits-struct.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
