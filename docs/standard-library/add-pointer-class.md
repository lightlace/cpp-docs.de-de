---
title: add_pointer-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_pointer
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
ms.openlocfilehash: fda2bcbd3484b9244d69358aac3e9baf5d37a4ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566009"
---
# <a name="addpointer-class"></a>add_pointer-Klasse

Wandelt einen angegebenen Typ in einen Zeiger auf den Typ um.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Das Element **Typedef** `type` benennt den gleichen Typ wie `remove_reference<T>::type*`. Der Alias `add_pointer_t` ist eine Verknüpfung für den Zugriff auf die Member **Typedef** `type`.

Da es unzulässig ist, einen Zeiger aus einem Verweis zu erstellen, wird der Verweis durch `add_pointer` ggf. vom angegebenen Typ entfernt, bevor der Zeiger auf den Typ erstellt wird. Daher können Sie einen Typ mit `add_pointer` verwenden, ohne sich überlegen zu müssen, ob der Typ ein Verweis ist.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, dass `add_pointer` eines Typs mit einem Zeiger auf diesen Typ identisch ist.

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_pointer_t<int> *p = (int **)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_pointer_t<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_pointer_t<int> == int *
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_pointer-Klasse](../standard-library/remove-pointer-class.md)<br/>
