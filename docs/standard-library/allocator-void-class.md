---
title: Allocator&lt;void&gt;-Klasse
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: 7ac7fbaa8c50eb13457271cf96ddc3412733c833
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245882"
---
# <a name="allocatorltvoidgt-class"></a>Allocator&lt;void&gt;-Klasse

Eine Spezialisierung der vorlagenklassenzuweisung zum Typ **"void"** , definieren die Typen, die in diesem Kontext sinnvoll.

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

Die Klasse spezialisiert explizit die Vorlagenklasse [Allocator](../standard-library/allocator-class.md) für Typ **"void"** . Dessen Konstruktoren und Zuweisungsoperator verhalten sich genauso wie für die Vorlagenklasse, aber sie definieren nur die folgenden Typen:

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [pointer](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- [rebind](../standard-library/allocator-class.md#rebind), eine geschachtelte Vorlagenklasse.
