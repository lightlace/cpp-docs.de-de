---
title: Compilerfehler C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 15f9ba62751d9b3cb17ab56659310292dab41adf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350451"
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