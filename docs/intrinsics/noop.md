---
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 24ba85b1fbbba4491c03d5a81afae345228db3bd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217184"
---
# <a name="__noop"></a>__noop

**Microsoft-spezifisch**

Der `__noop` systeminterne Wert gibt an, dass eine Funktion ignoriert werden soll. Die Argumentliste wird analysiert, aber es wird kein Code für die Argumente generiert. Es ist für die Verwendung in globalen Debugfunktionen vorgesehen, die eine Variable Anzahl von Argumenten akzeptieren.

Der Compiler konvertiert den `__noop` systeminternen zum Zeitpunkt der Kompilierung in 0.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie verwenden `__noop`können.

```cpp
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Schlüsselwörter](../cpp/keywords-cpp.md)
