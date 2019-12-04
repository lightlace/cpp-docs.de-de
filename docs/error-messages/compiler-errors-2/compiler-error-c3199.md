---
title: Compilerfehler C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 2f0ca98dc44a78adde378a0f80078ae30c590e11
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738816"
---
# <a name="compiler-error-c3199"></a>Compilerfehler C3199

Ungültige Verwendung von Gleit Komma-Pragmas: Ausnahmen werden im nicht präzisen Modus nicht unterstützt.

Das [float_control](../../preprocessor/float-control.md) -Pragma wurde verwendet, um ein Gleit Komma Ausnahmemodell unter einer [/FP](../../build/reference/fp-specify-floating-point-behavior.md) -Einstellung anzugeben, die nicht **/fp: präzise**ist.

Im folgenden Beispiel wird C3199 generiert:

```cpp
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```
