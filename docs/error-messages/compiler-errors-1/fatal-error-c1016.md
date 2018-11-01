---
title: Schwerwiegender Fehler C1016
ms.date: 11/04/2016
f1_keywords:
- C1016
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
ms.openlocfilehash: 7463c6962817716611f3571e073712f374773fa7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566035"
---
# <a name="fatal-error-c1016"></a>Schwerwiegender Fehler C1016

\#Ifdef erwartet, dass ein Bezeichner #ifndef ein Bezeichner erwartet.

In der Direktive für die bedingte Kompilierung ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) oder `#ifndef`) fehlt ein Bezeichner für die Auswertung. Geben Sie einen Bezeichner an, um den Fehler zu beheben.

Im folgenden Beispiel wird C1016 generiert:

```
// C1016.cpp
#ifdef   // C1016
#define FC1016
#endif

int main() {}
```

Mögliche Lösung:

```
// C1016b.cpp
#ifdef X
#define FC1016
#endif

int main() {}
```