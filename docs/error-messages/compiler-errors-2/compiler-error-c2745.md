---
title: Compilerfehler C2745
ms.date: 11/04/2016
f1_keywords:
- C2745
helpviewer_keywords:
- C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
ms.openlocfilehash: 53a218fd80c6b8261aa0dda6bcaa1c347db73458
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563995"
---
# <a name="compiler-error-c2745"></a>Compilerfehler C2745

"token": dieses Token kann nicht auf einen Bezeichner konvertiert werden

Bezeichner müssen aus zulässigen Zeichen bestehen.

Im folgende Beispiel wird die C2745 generiert:

```
// C2745.cpp
// compile with: /clr
int main() {
   int __identifier([));   // C2745
}
```