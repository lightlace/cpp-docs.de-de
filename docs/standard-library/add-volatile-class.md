---
title: add_volatile-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: ff48b1848e2d7631d789621a5ef845d04d8e8821
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495939"
---
# <a name="addvolatile-class"></a>add_volatile-Klasse

Stellt eine **flüchtige** Typ aus dem angegebenen Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz von `add_volatile<T>` verfügt über einen Member **Typedef** `type` , *T* Wenn *T* ist ein Verweis, eine Funktion oder ein Volatile-qualified-Typ, andernfalls **flüchtige** *T*. Der Alias `add_volatile_t` ist eine Verknüpfung für den Zugriff auf die Member **Typedef** `type`.

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

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_volatile-Klasse](../standard-library/remove-volatile-class.md)<br/>
