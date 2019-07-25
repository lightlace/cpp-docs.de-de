---
title: is_integral-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: a367bb06f49dd2c9c64f0c257a3573add5645efe
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456238"
---
# <a name="isintegral-class"></a>is_integral-Klasse

Testet, ob der Typ eine Ganzzahl ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true",  wenn die typität einer der ganzzahligen Typen `cv-qualified` oder ein Formular eines ganzzahligen Typs ist; andernfalls "false".

Ein ganzzahliger Typ ist "  **bool**", " **char**", " **Ganzzahl ohne Vorzeichen char**", " **signed char**, **wchar_t**", " **Short**", " **Ganzzahl ohne Vorzeichen Short**", " **int**", " **Ganzzahl ohne Vorzeichen int**", " **Long**" Mit Compilern, die Sie bereitstellen, kann ein ganzzahliger Typ außerdem einen von **Long Long**-, **Ganzzahl ohne Vorzeichen long long**-, **__int64**-und **Ganzzahl ohne Vorzeichen __int64**-Wert aufweisen.

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

[<type_traits>](../standard-library/type-traits.md)\
[is_enum-Klasse](../standard-library/is-enum-class.md)\
[is_floating_point-Klasse](../standard-library/is-floating-point-class.md)
