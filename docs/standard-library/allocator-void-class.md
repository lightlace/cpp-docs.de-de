---
title: Allocator&lt;void&gt;-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0585396d2cacc2bb41abf364e3d01ca81629146f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953553"
---
# <a name="allocatorltvoidgt-class"></a>Allocator&lt;void&gt;-Klasse

Eine Spezialisierung der vorlagenklassenzuweisung zum Typ **"void"**, definieren die Typen, die in diesem Kontext sinnvoll.

## <a name="syntax"></a>Syntax

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>Hinweise

Die Klasse spezialisiert explizit die Vorlagenklasse [Allocator](../standard-library/allocator-class.md) für Typ **"void"**. Dessen Konstruktoren und Zuweisungsoperator verhalten sich genauso wie für die Vorlagenklasse, aber sie definieren nur die folgenden Typen:

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [pointer](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- [rebind](../standard-library/allocator-class.md#rebind), eine geschachtelte Vorlagenklasse.

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
