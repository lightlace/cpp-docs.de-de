---
title: is_void-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_void
dev_langs:
- C++
helpviewer_keywords:
- is_void class
- is_void
ms.assetid: 99b0de3b-1b38-4949-b053-080e5363174e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3690eab417f4c817e571026e501f36a19671da2
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100988"
---
# <a name="isvoid-class"></a>is_void-Klasse

Testet, ob der Typ ein void-Typ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_void;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist **"void"** oder eine cv-qualifizierte Form von **"void"**, andernfalls ist Sie false.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_void.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_void<trivial> == " << std::boolalpha
        << std::is_void<trivial>::value << std::endl;
    std::cout << "is_void<void()> == " << std::boolalpha
        << std::is_void<void()>::value << std::endl;
    std::cout << "is_void<void> == " << std::boolalpha
        << std::is_void<void>::value << std::endl;

    return (0);
    }

```

```Output
is_void<trivial> == false
is_void<void()> == false
is_void<void> == true
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
