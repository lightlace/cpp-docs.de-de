---
title: Compilerfehler C2333
ms.date: 11/04/2016
f1_keywords:
- C2333
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
ms.openlocfilehash: e9119a8375a276a59cbf3a6db9541f6ccaef5122
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432632"
---
# <a name="compiler-error-c2333"></a>Compilerfehler C2333

'Funktion': Fehler in Funktionsdeklaration; Funktionstext wird übersprungen

Dieser Fehler tritt nach einem anderen Fehler, für die Member-Funktionen, die innerhalb ihrer Klasse definiert.

Im folgende Beispiel wird die C2333 generiert:

```
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```