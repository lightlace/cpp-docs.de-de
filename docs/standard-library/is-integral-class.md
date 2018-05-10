---
title: is_integral-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_integral
dev_langs:
- C++
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 531ee45aed64daa19f818bc5c8480a9c1b032d30
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="isintegral-class"></a>is_integral-Klasse

Testet, ob der Typ eine Ganzzahl ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der Typ `Ty` ein ganzzahliger Typ oder ein `cv-qualified`-Formular eines der ganzzahligen Typen ist, andernfalls ist sie „false“.

Ein ganzzahliger Typ ist entweder `bool`, `char`, `unsigned char`, `signed char`, `wchar_t`, `short`, `unsigned short`, `int`, `unsigned int`, `long` oder `unsigned long`. Mit Compilern kann der ganzzahlige Typ darüber hinaus `long long`, `unsigned long long`, `__int64` und `unsigned __int64` sein.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }

```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_enum-Klasse](../standard-library/is-enum-class.md)<br/>
[is_floating_point-Klasse](../standard-library/is-floating-point-class.md)<br/>
