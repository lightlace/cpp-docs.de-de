---
title: is_integral-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: c7d0d8b8572c26bfa75b9fab81900c0ae21fb932
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336492"
---
# <a name="isintegral-class"></a>is_integral-Klasse

Testet, ob der Typ eine Ganzzahl ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eines der ganzzahligen Typen oder ein `cv-qualified` -Form eines dieser die ganzzahligen Typen ist, andernfalls er false enthält.

Ein ganzzahliger Typ ist eine der **"bool"**, **Char**, **unsigned Char**, **signiert Char**, **"wchar_t"**, **kurze**, **unsigned short**, **Int**, **ganze Zahl ohne Vorzeichen**, **lange**, und **unsigned long**. Darüber hinaus mit Compilern, die sie bereitstellen, ein ganzzahliger Typ kann eine der **long long**, **long long ohne Vorzeichen**, **__int64**, und **__int64 ohne Vorzeichen**.

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
