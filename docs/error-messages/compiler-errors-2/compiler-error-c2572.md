---
title: Compilerfehler C2572
ms.date: 11/04/2016
f1_keywords:
- C2572
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
ms.openlocfilehash: 78402c054573de8c9860e96b6abe60ec5c3cfe38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621246"
---
# <a name="compiler-error-c2572"></a>Compilerfehler C2572

'class:: Member': Neudefinition des Standardparameters: Parameter Param

Standardparameter können nicht neu definiert werden. Wenn Sie einen anderen Wert für den Parameter, der Standardparameter nicht definiert werden soll benötigen.

Im folgende Beispiel wird die C2572 generiert:

```
// C2572.cpp
// compile with: /c
void f(int i = 1);   // function declaration

// function definition
void f(int i = 1) {}   // C2572

// try the following line instead
// void f(int i) {}
```