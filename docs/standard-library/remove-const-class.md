---
title: remove_const-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::remove_const
dev_langs:
- C++
helpviewer_keywords:
- remove_const class
- remove_const
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc546de0563b0a2732164ea2e5770a0b4145845f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="removeconst-class"></a>remove_const-Klasse

Wandelt einen Typ in einen nicht konstanten Typ um.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct remove_const;
```

```cpp
template <class T>
using remove_const_t = typename remove_const<T>::type;
```

### <a name="parameters"></a>Parameter

`T` Die zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz von `remove_const<T>` enthält einen geänderten Typ, der `T1` ist, wenn `T` das Format `const T1` hat; andernfalls `T`.

## <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_const_t<const int>*)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_const_t<const int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_const_t<const int> == int
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_const-Klasse](../standard-library/add-const-class.md)<br/>
[remove_cv-Klasse](../standard-library/remove-cv-class.md)<br/>
