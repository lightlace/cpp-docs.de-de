---
title: Compilerfehler C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: a08ac9f9cfbc332b90ad16c663349ee227427278
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446633"
---
# <a name="compiler-error-c2457"></a>Compilerfehler C2457

> "*Makro*': das vordefiniertes Makro kann nicht außerhalb eines Funktionsrumpfs angezeigt werden

Sie haben versucht, ein vordefiniertes Makro, verwenden Sie z. B. [ &#95; &#95;Funktion&#95;&#95;](../../preprocessor/predefined-macros.md), in einem globalen Bereich.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2457 generiert und zeigt auch die richtige Verwendung:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```