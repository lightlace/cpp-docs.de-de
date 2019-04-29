---
title: Compilerwarnung (Stufe 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: 54bc8931b5eaa3bbb5053e5c21aa2aaaa73126fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401513"
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