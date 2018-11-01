---
title: Compilerfehler C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: c20fcc7673c00ea7cfad32bdc3feae042f1f9086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445356"
---
# <a name="compiler-error-c2734"></a>Compilerfehler C2734

'Bezeichner': Konstantes Objekt muss initialisiert werden, wenn es nicht Extern

Der Bezeichner wurde deklariert `const` , aber nicht initialisiert oder `extern`.

Im folgende Beispiel wird die C2734 generiert:

```
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```