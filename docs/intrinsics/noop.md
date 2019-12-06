---
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: aec4df98413bf34ac1e2966d012bb905edd4775e
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857930"
---
# <a name="__noop"></a>__noop

**Microsoft-spezifisch**

Der `__noop` systeminterne Wert gibt an, dass eine Funktion ignoriert werden soll. Die Argumentliste wird analysiert, aber es wird kein Code für die Argumente generiert. Es ist für die Verwendung in globalen Debugfunktionen vorgesehen, die eine Variable Anzahl von Argumenten akzeptieren.

Der Compiler konvertiert die `__noop` intrinsisch zum Zeitpunkt der Kompilierung in 0.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie `__noop`verwenden können.

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

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

Systeminterne [Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Stichwörter](../cpp/keywords-cpp.md)
