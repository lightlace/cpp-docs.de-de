---
title: remove_cv-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_cv
dev_langs:
- C++
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b14733ea906fa47e7339c23efb8942763e928828
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956308"
---
# <a name="removecv-class"></a>remove_cv-Klasse

Wandelt einen Typ in einen nicht konstanten/permanenten Typ um.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct remove_cv;

template <class T>
using remove_cv_t = typename remove_cv<T>::type;
```

### <a name="parameters"></a>Parameter

*T* der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz von `remove_cv<T>` enthält einen geänderten Typ, der `T1` beim *T* hat das Format `const T1`, `volatile T1`, oder `const volatile T1`, andernfalls *T*.

## <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_cv_t<const volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_cv_t<const volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_cv_t<const volatile int> == int
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const-Klasse](../standard-library/remove-const-class.md)<br/>
[remove_volatile-Klasse](../standard-library/remove-volatile-class.md)<br/>
