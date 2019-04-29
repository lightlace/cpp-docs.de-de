---
title: is_placeholder-Klasse
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_placeholder
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
ms.openlocfilehash: 2c7848c88194a9b541867b26ffe27764ad862503
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413631"
---
# <a name="isplaceholder-class"></a>is_placeholder-Klasse

Testet, ob der Typ ein Platzhalter ist.

## <a name="syntax"></a>Syntax

struct is_placeholder { static const int value; };

## <a name="remarks"></a>Hinweise

Der konstante Wert `value` ist 0, wenn der Typ `Ty` kein Platzhalter ist; andernfalls ist der Wert die Position des Funktionsaufrufarguments, an die es gebunden wird. Sie verwenden es zum Bestimmen des Werts `N` für den N-ten Platzhalter `_N`.

## <a name="example"></a>Beispiel

```cpp
// std__functional__is_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

using namespace std::placeholders;

template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}
```

```Output
0
3
```

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[_1-Objekt](../standard-library/1-object.md)<br/>
