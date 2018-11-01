---
title: Compilerfehler C2193
ms.date: 11/04/2016
f1_keywords:
- C2193
helpviewer_keywords:
- C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
ms.openlocfilehash: 1eb1145b7927733ab82253632847da90542250fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574199"
---
# <a name="compiler-error-c2193"></a>Compilerfehler C2193

'Bezeichner': bereits in einem Segment

Eine Funktion wurde in zwei verschiedenen Segmenten platziert `alloc_text` und `code_seg` Pragmas.

Im folgende Beispiel wird die C2193 generiert:

```
// C2193.cpp
// compile with: /c
extern "C" void MYFUNCTION();
#pragma alloc_text(MYCODE, MYFUNCTION)
#pragma code_seg("MYCODE2")
extern "C" void MYFUNCTION() {}   // C2193
extern "C" void MYFUNCTION2() {}
```