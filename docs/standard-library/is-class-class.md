---
title: is_class-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_class
helpviewer_keywords:
- is_class class
- is_class
ms.assetid: 96fc34a3-a81b-4ec6-b7fb-baafde1a0f4e
ms.openlocfilehash: 7dc71622a37164e996b067276ddf8a5d1dd88b62
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456640"
---
# <a name="isclass-class"></a>is_class-Klasse

Testet, ob der Typ eine Klasse ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_class;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true", wenn der Typ " *Ty* " ein Typ ist, der als **Klasse** oder `cv-qualified` **Struktur**definiert ist, oder eine Instanz des typprädikats, andernfalls "false".

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_class.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_class<trivial> == " << std::boolalpha
        << std::is_class<trivial>::value << std::endl;
    std::cout << "is_class<int> == " << std::boolalpha
        << std::is_class<int>::value << std::endl;

    return (0);
    }
```

```Output
is_class<trivial> == true
is_class<int> == false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[is_compound-Klasse](../standard-library/is-compound-class.md)\
[is_union-Klasse](../standard-library/is-union-class.md)
