---
title: Compilerfehler C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 15f9ba62751d9b3cb17ab56659310292dab41adf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596780"
---
# <a name="compiler-error-c2588"></a>Compilerfehler C2588

":: ~ Identifier': Unzulässiger globaler-Destruktor

Der Destruktor wird für andere als eine Klasse, Struktur oder Union definiert. Dies ist nicht zulässig.

Dieser Fehler kann verursacht werden, durch eine fehlende Klasse, Struktur oder union Namen auf der linken Seite des Bereichsauflösungsoperators (`::`) Operator.

Im folgende Beispiel wird die C2588 generiert:

```
// C2588.cpp
~F();   // C2588
```