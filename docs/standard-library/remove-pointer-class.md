---
title: remove_pointer-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_pointer
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
ms.openlocfilehash: 786a1cba5fc35014e33e3e19245271adefec1372
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451251"
---
# <a name="removepointer-class"></a>remove_pointer-Klasse

Wandelt einen Zeiger auf den Typ in einen Typ um.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct remove_pointer;

template <class T>
using remove_pointer_t = typename remove_pointer<T>::type;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz von `remove_pointer<T>` enthält einen geänderten Typ, der ist `T1` , wenn *t* das `T1*`Format, `T1* volatile` `T1* const`, oder `T1* const volatile`hat, andernfalls *t*.

## <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_pointer_t<int *> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_pointer_t<int *> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_pointer_t<int *> == int
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[add_pointer-Klasse](../standard-library/add-pointer-class.md)
