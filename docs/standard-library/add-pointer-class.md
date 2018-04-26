---
title: add_pointer-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::add_pointer
dev_langs:
- C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 102984fc0384499f5aa2538a0f8d858578096551
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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

*T* der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Der typedef-Member `type` benennt den gleichen Typ mit `remove_reference<T>::type*`. Das Alias `add_pointer_t` ist eine Verknüpfung für den Zugriff auf den typedef-Member `type`.

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
