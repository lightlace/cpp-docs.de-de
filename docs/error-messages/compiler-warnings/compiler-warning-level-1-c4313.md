---
title: Compilerwarnung (Stufe 1) C4313
ms.date: 11/04/2016
f1_keywords:
- C4313
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
ms.openlocfilehash: 774af2d5d29112d56adf97e22d1bdd758a816ef1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352935"
---
# <a name="compiler-warning-level-1-c4313"></a>Compilerwarnung (Stufe 1) C4313

„Funktion“: „Formatbezeichner“ in der Formatzeichenfolge steht mit der Argumentennummer vom Typ „Typ“ in Konflikt.

Es besteht ein Konflikt zwischen dem angegebenen Format und dem Wert, den Sie übergeben. Beispielsweise haben Sie einen 64-Bit-Parameter an einen nicht qualifizierten Formatbezeichner „%d“ übergeben, wohingegen ein 32-Bit-Ganzzahl-Parameter erwartet wird. Diese Warnung ist nur aktiv, wenn der Code für 64-Bit-Ziele kompiliert wird.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird C4313 generiert, wenn dies für 64-Bit-Ziele kompiliert wird.

```
// C4313.cpp
// Compile by using: cl /W1 C4313.cpp
#include <stdio.h>
int main() {
   int * pI = 0;
   printf("%d", pI);   // C4313 on 64-bit platform code
   // Try one of the following lines instead:
   // printf("%p\n", pI);
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information
}
```