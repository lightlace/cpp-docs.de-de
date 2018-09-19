---
title: Compilerfehler C2164 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2164
dev_langs:
- C++
helpviewer_keywords:
- C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1e997a3b260b9ec8b68a92967233269707e6888
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032158"
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