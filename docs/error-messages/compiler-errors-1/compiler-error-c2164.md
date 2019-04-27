---
title: Compilerfehler C2164
ms.date: 11/04/2016
f1_keywords:
- C2164
helpviewer_keywords:
- C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
ms.openlocfilehash: 3b1c7a94dfca1c2767e14f96204ecda670c8a586
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174821"
---
# <a name="compiler-error-c2164"></a>Compilerfehler C2164

"Function": systeminterne Funktion nicht deklariert

Ein `intrinsic` Pragma verwendet eine nicht deklarierte Funktion (tritt nur beim **/Oi**). Oder der systeminterne Compilerfunktionen ohne Angabe der Headerdatei verwendet wurde.

Im folgende Beispiel wird die C2164 generiert:

```
// C2164.c
// compile with: /c
// processor: x86
// Uncomment the following line to resolve.
// #include "xmmintrin.h"
void b(float *p) {
   _mm_load_ss(p);   // C2164
}
```