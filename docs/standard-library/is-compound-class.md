---
title: is_compound-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_compound
dev_langs:
- C++
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54bc403b363a2ff5ff55a3555411952018940119
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="iscompound-class"></a>is_compound-Klasse

Testet, ob der angegebene Typ nicht grundlegend ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typs Prädikat enthält `false` Wenn der Typ des `Ty` ist ein grundlegender Typ ist (d. h., wenn [Is_fundamental](../standard-library/is-fundamental-class.md)\<"ty" > enthält `true`) ist, andernfalls enthält er `true`. Daher enthält das Prädikat `true`, wenn `Ty` ein Arraytyp, ein Funktionstyp, ein Zeiger auf `void` oder auf ein Objekt oder eine Funktion, ein Verweis, eine Klasse, eine Vereinigung, eine Enumeration oder ein Zeiger auf ein nicht-statisches Klassenmember oder eine *cv-qualified*-Form eines dieser Elemente ist.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_compound.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_compound<trivial> == " << std::boolalpha
        << std::is_compound<trivial>::value << std::endl;
    std::cout << "is_compound<int[]> == " << std::boolalpha
        << std::is_compound<int[]>::value << std::endl;
    std::cout << "is_compound<int()> == " << std::boolalpha
        << std::is_compound<int()>::value << std::endl;
    std::cout << "is_compound<int&> == " << std::boolalpha
        << std::is_compound<int&>::value << std::endl;
    std::cout << "is_compound<void *> == " << std::boolalpha
        << std::is_compound<void *>::value << std::endl;
    std::cout << "is_compound<int> == " << std::boolalpha
        << std::is_compound<int>::value << std::endl;

    return (0);
    }

```

```Output
is_compound<trivial> == true
is_compound<int[]> == true
is_compound<int()> == true
is_compound<int&> == true
is_compound<void *> == true
is_compound<int> == false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_class-Klasse](../standard-library/is-class-class.md)<br/>
