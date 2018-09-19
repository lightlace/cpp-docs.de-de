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
ms.openlocfilehash: c44288c990f773984492f7c05b80423b17c1a37c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110577"
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
