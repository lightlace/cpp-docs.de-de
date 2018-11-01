---
title: Compilerfehler C3182
ms.date: 11/04/2016
f1_keywords:
- C3182
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
ms.openlocfilehash: 6866c7bbcee0a4097e490b344c79a6eec7f94570
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626745"
---
# <a name="compiler-error-c3182"></a>Compilerfehler C3182

'Klasse': eine using- oder Zugriffsdeklaration für Member ist innerhalb eines verwalteten oder WinRTtype nicht zulässig

Ein [mit](../../cpp/using-declaration.md) Deklaration ist in sämtlichen verwalteten Klassen unzulässig.

Im folgenden Beispiel wird C3182 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3182a.cpp
// compile with: /clr /c
ref struct B {
   void mf(int) {
   }
};

ref struct D : B {
   using B::mf;   // C3182, delete to resolve
   void mf(char) {
   }
};
```
