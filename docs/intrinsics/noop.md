---
title: __noop | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __noop_cpp
- __noop
dev_langs:
- C++
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97820367f0960925dfcac1db339260cd3f52b8bc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430214"
---
# <a name="noop"></a>__noop

**Microsoft-spezifisch**

Die `__noop` systeminterne gibt an, dass eine Funktion, die ignoriert werden sollen und die Argumentliste analysiert werden, jedoch kein Code generiert werden, für die Argumente. Es dient zur Verwendung in globalen Debugfunktionen, die eine Variable Anzahl von Argumenten akzeptieren.

Der Compiler konvertiert die `__noop` systeminterne 0 zum Zeitpunkt der Kompilierung.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie verwenden können `__noop`.

```
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

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)