---
title: Compilerwarnung (Stufe 4) C4668
ms.date: 11/04/2016
f1_keywords:
- C4668
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
ms.openlocfilehash: 84834ce0f980502e16a8398d35da85d1a005c9cb
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990551"
---
# <a name="compiler-warning-level-4-c4668"></a>Compilerwarnung (Stufe 4) C4668

'Symbol' ist nicht als ein Präprozessormakro definiert, wird durch '0' für 'Anweisungen' ersetzt

Ein Symbol, das nicht definiert wurde, wurde mit einer Präprozessordirektive verwendet. Das Symbol wird zu "false" ausgewertet. Zum Definieren eines Symbols können Sie entweder die [#define Direktive](../../preprocessor/hash-define-directive-c-cpp.md) oder die [/D](../../build/reference/d-preprocessor-definitions.md) -Compileroption verwenden.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4668 generiert:

```cpp
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
