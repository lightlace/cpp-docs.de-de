---
title: Compilerfehler C3032
ms.date: 11/04/2016
f1_keywords:
- C3032
helpviewer_keywords:
- C3032
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
ms.openlocfilehash: 8e103d36bf3e49cfbb0a3724c044794601aabcee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256834"
---
# <a name="compiler-error-c3032"></a>Compilerfehler C3032

"var": Die Variable in der Klausel-Klausel kann keinen unvollständigen Typ "Typ" aufweisen.

Typen, die an bestimmte Klauseln übergeben werden, müssen für den Compiler vollständig sichtbar sein.

Im folgenden Beispiel wird C3032 generiert:

```
// C3032.cpp
// compile with: /openmp /link vcomps.lib
#include "omp.h"

struct Incomplete;
extern struct Incomplete inc;

int main() {
   int i = 9;
   #pragma omp parallel private(inc)   // C3032
      ;

   #pragma omp parallel private(i)     // OK
      ;

}
```