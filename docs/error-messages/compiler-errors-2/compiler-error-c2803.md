---
title: Compilerfehler C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d20b8dde9f4134273adcba0f947f685f7ce7d213
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447267"
---
# <a name="compiler-error-c2803"></a>Compilerfehler C2803

'Operator Operator' muss mindestens einen formalen Parameter des Klassentyps haben.

Der überladene Operator hat einen Parameter vom Klassentyp.

Müssen Sie mindestens einen Parameter als Verweis (nicht mit Zeigern, sondern Verweise) oder anhand des Werts zu schreiben können übergeben "ein < b" (ein und b von Typklasse-A).

Wenn beide Parameter Zeiger ein reiner Vergleich der Zeigeradressen werden und die benutzerdefinierte Konvertierung wird nicht verwendet.

Im folgende Beispiel wird die C2803 generiert:

```
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```