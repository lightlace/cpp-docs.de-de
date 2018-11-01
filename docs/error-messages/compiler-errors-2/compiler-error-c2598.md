---
title: Compilerfehler C2598
ms.date: 11/04/2016
f1_keywords:
- C2598
helpviewer_keywords:
- C2598
ms.assetid: 40777c62-39ba-441e-b081-f49f94b43547
ms.openlocfilehash: 521a67bdf1e1f64853a3f87933b3fa714c8e33f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578229"
---
# <a name="compiler-error-c2598"></a>Compilerfehler C2598

Verknüpfungsspezifikation muss im globalen Gültigkeitsbereich sein.

Der Bindungsspezifizierer wird im lokalen Gültigkeitsbereich deklariert werden.

Im folgende Beispiel wird die C2598 generiert:

```
// C2598.cpp
// compile with: /c
void func() {
   extern "C" int func2();   // C2598
}

extern "C" int func( int i );
```