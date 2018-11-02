---
title: Compilerfehler C2082
ms.date: 11/04/2016
f1_keywords:
- C2082
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
ms.openlocfilehash: 8bfb54dc91ef9132e3930e2c0799070f80f5cd0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577254"
---
# <a name="compiler-error-c2082"></a>Compilerfehler C2082

Neudefinition des formalen Parameters "Bezeichner"

Ein formaler Parameter einer Funktion wird im Funktionsrumpf erneut deklariert. Um den Fehler zu beheben, entfernen Sie die Neudefinition.

Im folgenden Beispiel wird C2082 generiert.

```
// C2082.cpp
void func(int i) {
   int i;   // C2082
   int ii;   // OK
}
```