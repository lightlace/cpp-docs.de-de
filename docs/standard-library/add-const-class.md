---
title: add_const-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_const
dev_langs:
- C++
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eff64a70b2a666a6df081601c0e2a24f04563317
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954066"
---
# <a name="addconst-class"></a>add_const-Klasse

Erstellt den „const“-Typ aus „type“.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>Parameter

*Ty* der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typmodifizierers enthält einen geänderten Typ, der *Ty* Wenn *Ty* ist ein Verweis, eine Funktion oder ein konstant qualifizierter Typ ist, andernfalls `const Ty`.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const-Klasse](../standard-library/remove-const-class.md)<br/>
