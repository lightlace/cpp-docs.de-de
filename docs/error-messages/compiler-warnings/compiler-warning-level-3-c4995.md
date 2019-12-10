---
title: Compilerwarnung (Stufe 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: c361563c2272da002a0edc185cc924c64f6b5e5c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991662"
---
# <a name="compiler-warning-level-3-c4995"></a>Compilerwarnung (Stufe 3) C4995

"Function": der Name wurde als veraltet markiert #Pragma

Der Compiler hat eine Funktion gefunden, die als [veraltet](../../preprocessor/deprecated-c-cpp.md)markiert wurde. Die Funktion wird in zukünftigen Releases u. U. nicht mehr unterstützt. Sie können diese Warnung mit dem [Warning](../../preprocessor/warning.md) -Pragma deaktivieren (Beispiel unten).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4995 generiert:

```cpp
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
