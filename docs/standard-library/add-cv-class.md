---
title: add_cv-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_cv
dev_langs:
- C++
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9bdb00c421e668313d92c829c4252c2637e2e18
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722136"
---
# <a name="addcv-class"></a>add_cv-Klasse

Macht **const Volatile** Typ vom Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct add_cv;

template <class T>
using add_cv_t = typename add_cv<T>::type;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz von den geänderten Typ `add_cv<T>` verfügt über eine `type` Member **Typedef** entspricht *T* geändert, indem beide [Add_volatile](../standard-library/add-volatile-class.md) und [ Add_const](../standard-library/add-const-class.md), es sei denn, *T* bereits verfügt über die cv-Qualifizierer, ist ein Verweis oder eine Funktion.

Das `add_cv_t<T>`-Hilfsprogramm ist eine Verknüpfung für den Zugriff auf den `add_cv<T>`typedef-Member`type`.

## <a name="example"></a>Beispiel

```cpp
// add_cv.cpp
// compile by using: cl /EHsc /W4 add_cv.cpp
#include <type_traits>
#include <iostream>

struct S {
    void f() {
        std::cout << "invoked non-cv-qualified S.f()" << std::endl;
    }
    void f() const {
        std::cout << "invoked const S.f()" << std::endl;
    }
    void f() volatile {
        std::cout << "invoked volatile S.f()" << std::endl;
    }
    void f() const volatile {
        std::cout << "invoked const volatile S.f()" << std::endl;
    }
};

template <class T>
void invoke() {
    T t;
    ((T *)&t)->f();
}

int main()
{
    invoke<S>();
    invoke<std::add_const<S>::type>();
    invoke<std::add_volatile<S>::type>();
    invoke<std::add_cv<S>::type>();
}
```

```Output
invoked non-cv-qualified S.f()
invoked const S.f()
invoked volatile S.f()
invoked const volatile S.f()
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const-Klasse](../standard-library/remove-const-class.md)<br/>
[remove_volatile-Klasse](../standard-library/remove-volatile-class.md)<br/>
