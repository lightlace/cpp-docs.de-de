---
title: is_member_pointer-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_member_pointer
helpviewer_keywords:
- is_member_pointer class
- is_member_pointer
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
ms.openlocfilehash: 34a89f508e0dfa8b31f4e811e8edb3a0a4ba0eaf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633542"
---
# <a name="ismemberpointer-class"></a>is_member_pointer-Klasse

Testet, ob der Typ ein Zeiger auf den Member ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_member_pointer;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist ein Zeiger auf eine Memberfunktion oder ein Zeiger auf ein Memberobjekt oder ein `cv-qualified` -Formular von einem davon ist, andernfalls er false enthält.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_member_pointer.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct functional
    {
    int f();
    };

int main()
    {
    std::cout << "is_member_pointer<trivial *> == "
        << std::boolalpha
        << std::is_member_pointer<trivial *>::value
        << std::endl;
    std::cout << "is_member_pointer<int trivial::*> == "
        << std::boolalpha
        << std::is_member_pointer<int trivial::*>::value
        << std::endl;
    std::cout << "is_member_pointer<int (functional::*)()> == "
        << std::boolalpha
        << std::is_member_pointer<int (functional::*)()>::value
        << std::endl;

    return (0);
    }

```

```Output
is_member_pointer<trivial *> == false
is_member_pointer<int trivial::*> == true
is_member_pointer<int (functional::*)()> == true
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_member_function_pointer-Klasse](../standard-library/is-member-function-pointer-class.md)<br/>
[is_member_object_pointer-Klasse](../standard-library/is-member-object-pointer-class.md)<br/>
[is_pointer-Klasse](../standard-library/is-pointer-class.md)<br/>
