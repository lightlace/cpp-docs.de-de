---
title: Compilerfehler C2353
ms.date: 11/04/2016
f1_keywords:
- C2353
helpviewer_keywords:
- C2353
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
ms.openlocfilehash: 3cfcb544349adc0b7b4e13472f70aac382f958fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516995"
---
# <a name="compiler-error-c2353"></a>Compilerfehler C2353

Ausnahmespezifikation ist nicht zulässig.

Ausnahmespezifikationen sind in Memberfunktionen von verwalteten Klassen nicht zulässig.

Im folgende Beispiel wird die C2353 generiert:

```
// C2353.cpp
// compile with: /clr /c
ref class X {
   void f() throw(int);   // C2353
   void f();   // OK
};
```