---
title: is_placeholder-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::is_placeholder
dev_langs:
- C++
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b577803f766d8f5cafa054e84b5b7ec0f152480b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[_1-Objekt](../standard-library/1-object.md)<br/>
