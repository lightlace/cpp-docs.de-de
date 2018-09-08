---
title: is_arithmetic-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_arithmetic
dev_langs:
- C++
helpviewer_keywords:
- is_arithmetic class
- is_arithmetic
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72ab821d32b63800c9edeaef070bd745ef8eae86
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108875"
---
# <a name="isarithmetic-class"></a>is_arithmetic-Klasse

Prüft, ob der Typ arithmetisch ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_arithmetic;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist ein arithmetischer Typ, d. h. ein ganzzahliger Typ oder einen Gleitkommawert lassen, oder ein `cv-qualified` -Formular von einem davon ist, andernfalls er false enthält.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_arithmetic.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_arithmetic<trivial> == " << std::boolalpha
        << std::is_arithmetic<trivial>::value << std::endl;
    std::cout << "is_arithmetic<int> == " << std::boolalpha
        << std::is_arithmetic<int>::value << std::endl;
    std::cout << "is_arithmetic<float> == " << std::boolalpha
        << std::is_arithmetic<float>::value << std::endl;

    return (0);
    }
```

```Output
is_arithmetic<trivial> == false
is_arithmetic<int> == true
is_arithmetic<float> == true
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_floating_point-Klasse](../standard-library/is-floating-point-class.md)<br/>
[is_integral-Klasse](../standard-library/is-integral-class.md)<br/>
