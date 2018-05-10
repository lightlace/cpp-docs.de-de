---
title: add_volatile-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf15ef0b5134af7831cf2e71b4235df9534f3425
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="addvolatile-class"></a>add_volatile-Klasse

Wandelt einen angegebenen Typ in einen volatile-Typ um.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Parameter

*T* der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des `add_volatile<T>` enthält einen geänderten typedef-Member`type`, der *T* ist, wenn *T* ein Verweis, eine Funktion oder ein volatile-qualified-Typ ist; andernfalls `volatile` *T*. Das Alias `add_volatile_t` ist eine Verknüpfung für den Zugriff auf den typedef-Member`type`.

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
