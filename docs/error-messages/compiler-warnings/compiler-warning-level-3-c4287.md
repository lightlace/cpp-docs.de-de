---
title: Compilerwarnung (Stufe 3) C4287
ms.date: 11/04/2016
f1_keywords:
- C4287
helpviewer_keywords:
- C4287
ms.assetid: 1bf3bff8-6402-4d06-95ba-431678a790a7
ms.openlocfilehash: b37e0692a63f02dc96dec8717d4defd64d7183ac
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051676"
---
# <a name="compiler-warning-level-3-c4287"></a>Compilerwarnung (Stufe 3) C4287

"Operator": nicht signierte/negative Konstante stimmen nicht überein.

Eine nicht signierte Variable wurde in einem Vorgang mit einer negativen Zahl verwendet.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4287 generiert:

```cpp
// C4287.cpp
// compile with: /W3
#pragma warning(default : 4287)
#include <stdio.h>

int main()
{
    unsigned int u = 1;
    if (u < -1)   // C4287
        printf_s("u LT -1");
    else
        printf_s("u !LT -1");
    return 0;
}
```