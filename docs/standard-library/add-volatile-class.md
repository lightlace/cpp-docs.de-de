---
title: add_volatile-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: becea4ff52342a79d0b87ffe0022e2cf84c47949
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456534"
---
# <a name="addvolatile-class"></a>add_volatile-Klasse

Wandelt einen **flüchtigen** Typ aus dem angegebenen Typ um.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz von `add_volatile<T>` verfügt über einen Member **typedef** `type` , der *t* ist, wenn *t* ein Verweis, eine Funktion oder ein flüchtiger qualifizierter Typ ist; andernfalls **flüchtig** *t*. Der Alias `add_volatile_t` ist eine Verknüpfung für den Zugriff auf die **typedef** `type`-Member.

## <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[remove_volatile-Klasse](../standard-library/remove-volatile-class.md)
