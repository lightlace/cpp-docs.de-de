---
title: Compilerfehler C2637
ms.date: 11/04/2016
f1_keywords:
- C2637
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
ms.openlocfilehash: 4231a811911fdf600b47962e929f6f3cff1f1bca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602534"
---
# <a name="compiler-error-c2637"></a>Compilerfehler C2637

'Bezeichner': Zeiger auf Datenmember kann nicht geändert werden.

Ein Zeiger auf ein Datenmember kann nicht durch eine Aufrufkonvention verfügen. Um zu beheben, entfernen Sie die Aufrufkonvention oder deklarieren Sie einen Zeiger auf eine Memberfunktion zu.

Im folgende Beispiel wird die C2637 generiert:

```
// C2637.cpp
// compile with: /c
struct S {};
int __stdcall S::*pms1;   // C2637

// OK
int S::*pms2;
int (__stdcall S::*pms3)(...);
```