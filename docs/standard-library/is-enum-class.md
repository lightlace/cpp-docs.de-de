---
title: is_enum-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_enum
helpviewer_keywords:
- is_enum class
- is_enum
ms.assetid: df3b00b7-4f98-4b3a-96ce-10ad958ee69c
ms.openlocfilehash: 623bda13a12ac311618e1b9fffdbc3f676013df6
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517584"
---
# <a name="isenum-class"></a>is_enum-Klasse

Testet, ob der Typ eine Enumeration ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_enum;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist ein Enumerationstyp oder ein `cv-qualified` bestehen aus einem Enumerationstyp ist, andernfalls er false enthält.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_enum.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

enum color {
    red, greed, blue};

int main()
    {
    std::cout << "is_enum<trivial> == " << std::boolalpha
        << std::is_enum<trivial>::value << std::endl;
    std::cout << "is_enum<color> == " << std::boolalpha
        << std::is_enum<color>::value << std::endl;
    std::cout << "is_enum<int> == " << std::boolalpha
        << std::is_enum<int>::value << std::endl;

    return (0);
    }
```

```Output
is_enum<trivial> == false
is_enum<color> == true
is_enum<int> == false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_integral-Klasse](../standard-library/is-integral-class.md)<br/>
