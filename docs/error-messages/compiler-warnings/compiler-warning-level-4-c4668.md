---
title: Compilerwarnung (Stufe 4) C4668 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4668
dev_langs:
- C++
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c960eb2cc79298977c8d7c91808b0a5492d05758
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073999"
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