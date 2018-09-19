---
title: Compilerwarnung (Stufe 3) C4995 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4995
dev_langs:
- C++
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5ae389fef72681c6a8b31c9790c6773535f467d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053478"
---
# <a name="compiler-warning-level-3-c4995"></a>Compilerwarnung (Stufe 3) C4995

'Funktion': Name wurde als #pragma als veraltet markiert

Der Compiler hat festgestellt, eine Funktion, die mit dem Pragma [veraltet](../../preprocessor/deprecated-c-cpp.md). Die Funktion wird in zukünftigen Releases u. U. nicht mehr unterstützt. Sie können diese Warnung deaktivieren, mit der [Warnung](../../preprocessor/warning.md) Pragma (nachfolgendes Beispiel).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4995 generiert:

```
// C4995.cpp
// compile with: /W3
#include <stdio.h>

// #pragma warning(disable : 4995)
void func1(void)
{
    printf("\nIn func1");
}

int main()
{
    func1();
    #pragma deprecated(func1)
    func1();   // C4995
}
```