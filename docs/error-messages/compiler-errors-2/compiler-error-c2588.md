---
title: Compilerfehler C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: f1f73e2585606e7e86213607a96ef713345419c1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755407"
---
# <a name="compiler-error-c2588"></a>Compilerfehler C2588

":: ~ Identifier": Ungültiger globaler Dekonstruktor

Der destrukturtor ist für etwas anderes als eine Klasse, Struktur oder Union definiert. Dieser Vorgang ist nicht zulässig.

Dieser Fehler kann durch eine fehlende Klassen-, Struktur-oder Union-Name auf der linken Seite des Bereichs Auflösungs Operators (`::`) verursacht werden.

Im folgenden Beispiel wird C2588 generiert:

```cpp
// C2588.cpp
~F();   // C2588
```
