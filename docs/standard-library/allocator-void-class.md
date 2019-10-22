---
title: Allocator&lt;void&gt;-Klasse
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: c8d787fe03dfe6f67fb8e228308ec74b6e7f620a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688532"
---
# <a name="allocatorltvoidgt-class"></a>Allocator&lt;void&gt;-Klasse

Eine Spezialisierung der Klassen Vorlagen Zuweisung zum Typ " **void**", die die Typen definiert, die in diesem Kontext sinnvoll sind.

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

Die Klasse spezialisiert explizit die Klassen Vorlagen [Zuweisung](../standard-library/allocator-class.md) für den Typ " **void**". Die Konstruktoren und der Zuweisungs Operator Verhalten sich genauso wie für die Klassen Vorlage, Sie definieren jedoch nur die folgenden Typen:

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [pointer](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- [binden](../standard-library/allocator-class.md#rebind), eine Vorlage für eine vorgebundene Klasse.
