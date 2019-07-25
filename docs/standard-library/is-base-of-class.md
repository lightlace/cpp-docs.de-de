---
title: is_base_of-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_base_of
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
ms.openlocfilehash: d56222f218033d00583e5e3def9790720ef7bb94
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456622"
---
# <a name="isbaseof-class"></a>is_base_of-Klasse

Testet, ob ein Typ die Basis eines anderen ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Base, class Derived>
struct is_base_of;
```

### <a name="parameters"></a>Parameter

*Sock*\
Die Basisklasse zum Testen.

*Gewonnen*\
Der abgeleitete Typ zum Testen.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true",  wenn die typbasis eine Basisklasse des *abgeleiteten*Typs ist; andernfalls "false".

## <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_base_of<base, base> == " << std::boolalpha
        << std::is_base_of<base, base>::value << std::endl;
    std::cout << "is_base_of<base, derived> == " << std::boolalpha
        << std::is_base_of<base, derived>::value << std::endl;
    std::cout << "is_base_of<derived, base> == " << std::boolalpha
        << std::is_base_of<derived, base>::value << std::endl;

    return (0);
    }
```

```Output
is_base_of<base, base> == true
is_base_of<base, derived> == true
is_base_of<derived, base> == false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[is_convertible-Klasse](../standard-library/is-convertible-class.md)
