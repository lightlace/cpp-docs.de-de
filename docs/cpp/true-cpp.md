---
title: "\"true\" (C++) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- true_cpp
dev_langs:
- C++
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e43fbfd9b3cff9ea617238ed7b4cccd08f780cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018703"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>Syntax

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>Hinweise

Dieses Schlüsselwort ist einer der beiden Werte für eine Variable vom Typ ["bool"](../cpp/bool-cpp.md) oder ein bedingter Ausdruck (ein bedingter Ausdruck ist jetzt boolescher Ausdruck "true"). Wenn `i` ist vom Typ **"bool"**, klicken Sie dann die Anweisung `i = true;` weist **"true"** zu `i`.

## <a name="example"></a>Beispiel

```cpp
// bool_true.cpp
#include <stdio.h>
int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)