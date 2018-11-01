---
title: is_compound-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_compound
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
ms.openlocfilehash: ea878af96908478b1956deee3858a9d2f48c2f0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502075"
---
# <a name="iscompound-class"></a>is_compound-Klasse

Testet, ob der angegebene Typ nicht grundlegend ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats enthält **"false"** Wenn der Typ des *Ty* ein grundlegender Typ ist (d. h., wenn [Is_fundamental](../standard-library/is-fundamental-class.md)\<Ty > enthält  **"true"**); Andernfalls ist es **"true"**. Daher enthält das Prädikat **"true"** Wenn *Ty* ist ein Arraytyp, ein Funktionstyp, ein Zeiger auf **"void"** oder ein Objekt oder eine Funktion, einen Verweis, eine Klasse, eine Union, eine Enumeration oder Zeiger auf nicht statische Klassenmember, oder ein *cv-qualifizierte* Form eines dieser Elemente.

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
