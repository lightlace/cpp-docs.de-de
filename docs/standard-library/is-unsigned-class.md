---
title: is_unsigned-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_unsigned
helpviewer_keywords:
- is_unsigned class
- is_unsigned
ms.assetid: ba5bec3d-796b-4e54-8595-a3941ec6a8dc
ms.openlocfilehash: 3da9f71543815b507307f2cf4969e8f19c79e8c5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458879"
---
# <a name="isunsigned-class"></a>is_unsigned-Klasse

Prüft, ob der Typ eine Ganzzahl ohne Vorzeichen ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_unsigned;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true",  wenn die typität ein ganzzahliger Typ `cv-qualified` ohne Vorzeichen oder ein ganzzahliger Typ ohne Vorzeichen ist; andernfalls "false".

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_unsigned.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_unsigned<trivial> == " << std::boolalpha
        << std::is_unsigned<trivial>::value << std::endl;
    std::cout << "is_unsigned<int> == " << std::boolalpha
        << std::is_unsigned<int>::value << std::endl;
    std::cout << "is_unsigned<unsigned int> == " << std::boolalpha
        << std::is_unsigned<unsigned int>::value << std::endl;
    std::cout << "is_unsigned<float> == " << std::boolalpha
        << std::is_unsigned<float>::value << std::endl;

    return (0);
    }
```

```Output
is_unsigned<trivial> == false
is_unsigned<int> == false
is_unsigned<unsigned int> == true
is_unsigned<float> == false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[is_signed-Klasse](../standard-library/is-signed-class.md)
