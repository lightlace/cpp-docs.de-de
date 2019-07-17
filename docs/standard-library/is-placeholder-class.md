---
title: is_placeholder-Klasse
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_placeholder
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
ms.openlocfilehash: 9fa7d4aaade6244fe26f89f3a667598d39471a47
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245160"
---
# <a name="isplaceholder-class"></a>is_placeholder-Klasse

Testet, ob der Typ ein Platzhalter ist.

## <a name="syntax"></a>Syntax

Struktur Is_placeholder {static const Int-Wert;};

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
