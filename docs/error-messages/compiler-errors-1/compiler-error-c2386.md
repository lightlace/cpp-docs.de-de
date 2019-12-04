---
title: Compilerfehler C2386
ms.date: 11/04/2016
f1_keywords:
- C2386
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
ms.openlocfilehash: 1ac58d63498df32488c1a0743aa6ad9f7b77b7ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745108"
---
# <a name="compiler-error-c2386"></a>Compilerfehler C2386

'symbol': Ein Symbol mit diesem Namen ist bereits im aktuellen Bereich vorhanden.

Sie haben versucht, einen Namespacealias zu erstellen, aber der ausgewählte Name ist bereits vorhanden.

Das folgende Beispiel generiert C2386:

```cpp
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```
