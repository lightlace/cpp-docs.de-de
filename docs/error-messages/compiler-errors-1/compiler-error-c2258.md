---
title: Compilerfehler C2258
ms.date: 11/04/2016
f1_keywords:
- C2258
helpviewer_keywords:
- C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
ms.openlocfilehash: 99936026929bbaad321abfaa106df41b99c5d19d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587797"
---
# <a name="compiler-error-c2258"></a>Compilerfehler C2258

Ungültige Syntax für rein virtuelle Methode; "= 0" erforderlich

Eine reine virtuelle Funktion ist mit einer falschen Syntax deklariert.

Im folgenden Beispiel wird C2258 generiert:

```
// C2258.cpp
// compile with: /c
class A {
public:
   void virtual func1() = 1; // C2258
   void virtual func2() = 0;   // OK
};
```