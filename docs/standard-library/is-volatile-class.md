---
title: is_volatile-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_volatile
dev_langs:
- C++
helpviewer_keywords:
- is_volatile class
- is_volatile
ms.assetid: 54922e8a-db4e-4cae-8931-b3352f0b8d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8e3ec18d00c50db29c6a08956d4c3375a4dc7ae
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962383"
---
# <a name="isvolatile-class"></a>is_volatile-Klasse

Testet, ob der Typ flüchtig ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_volatile;
```

### <a name="parameters"></a>Parameter

*Ty* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn *Ty* ist `volatile-qualified`.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_volatile.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_volatile<trivial> == " << std::boolalpha
        << std::is_volatile<trivial>::value << std::endl;
    std::cout << "is_volatile<volatile trivial> == " << std::boolalpha
        << std::is_volatile<volatile trivial>::value << std::endl;
    std::cout << "is_volatile<int> == " << std::boolalpha
        << std::is_volatile<int>::value << std::endl;
    std::cout << "is_volatile<volatile int> == " << std::boolalpha
        << std::is_volatile<volatile int>::value << std::endl;

    return (0);
    }

```

```Output
is_volatile<trivial> == false
is_volatile<volatile trivial> == true
is_volatile<int> == false
is_volatile<volatile int> == true
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_const-Klasse](../standard-library/is-const-class.md)<br/>
