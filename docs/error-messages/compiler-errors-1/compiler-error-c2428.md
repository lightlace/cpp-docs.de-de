---
title: Compilerfehler C2428
ms.date: 11/04/2016
f1_keywords:
- C2428
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
ms.openlocfilehash: 299a4e899a41bf47eec5eaf5b54d2307e557078e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614668"
---
# <a name="compiler-error-c2428"></a>Compilerfehler C2428

'Operation': für Operanden vom Typ "Bool" nicht zulässig

Dekrementoperatoren kann nicht angewendet werden, um Objekte des Typs `bool`.

Im folgende Beispiel wird die C2428 generiert:

```
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```