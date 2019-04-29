---
title: bad_weak_ptr-Klasse
ms.date: 11/04/2016
f1_keywords:
- memory/std::bad_weak_ptr
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
ms.openlocfilehash: 78438ef3378e5002396eecb32b9b7a76d5b50325
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377490"
---
# <a name="badweakptr-class"></a>bad_weak_ptr-Klasse

Meldet eine ungültige weak_ptr-Ausnahme.

## <a name="syntax"></a>Syntax

```cpp
class bad_weak_ptr : public std::exception
{
public:
    bad_weak_ptr();
    const char *what() throw();
};
```

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt eine Ausnahme, die von dem [shared_ptr-Klasse](../standard-library/shared-ptr-class.md)-Konstruktor ausgelöst werden kann, der ein Argument des Typs [weak_ptr-Klasse](../standard-library/weak-ptr-class.md) verwendet. Die Memberfunktion `what` gibt `"bad_weak_ptr"` zurück.

## <a name="example"></a>Beispiel

```cpp
// std__memory__bad_weak_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int);
        wp = sp;
    }

    try
    {
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired
    }
    catch (const std::bad_weak_ptr&)
    {
        std::cout << "bad weak pointer" << std::endl;
    }
    catch (...)
    {
        std::cout << "unknown exception" << std::endl;
    }

    return (0);
}
```

```Output
bad weak pointer
```

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[weak_ptr-Klasse](../standard-library/weak-ptr-class.md)<br/>
