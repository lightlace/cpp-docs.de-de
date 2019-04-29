---
title: Compilerwarnung (Stufe 4) C4668
ms.date: 11/04/2016
f1_keywords:
- C4668
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
ms.openlocfilehash: 11d96941a1efddde87068af8829e24259f2fa312
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408159"
---
# <a name="compiler-warning-level-4-c4668"></a>Compilerwarnung (Stufe 4) C4668

'Symbol' ist nicht als ein Präprozessormakro definiert, wird durch '0' für 'Anweisungen' ersetzt

Ein Symbol, das nicht definiert wurde, wurde mit einer Präprozessordirektive verwendet. Das Symbol wird auf "false" ausgewertet. Um ein Symbol definieren möchten, verwenden Sie entweder die [#define-Anweisung](../../preprocessor/hash-define-directive-c-cpp.md) oder [/d](../../build/reference/d-preprocessor-definitions.md) -Compileroption.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4668 generiert:

```
// C4668.cpp
// compile with: /W4
#include <stdio.h>

#pragma warning (default : 4668)   // turn warning on

int main()
{
    #if q   // C4668, q is not defined
        printf_s("defined");
    #else
        printf_s("undefined");
    #endif
}
```