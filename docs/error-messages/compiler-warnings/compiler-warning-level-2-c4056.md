---
title: Compilerwarnung (Stufe 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 20e7c2693c14c0ea05cc6f07f8dad4ce76c1ef5e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052195"
---
# <a name="compiler-warning-level-2-c4056"></a>Compilerwarnung (Stufe 2) C4056

Überlauf bei Gleit Komma Konstanten-Arithmetik

Bei der arithmetischen Gleit Komma Konstanten wird ein Ergebnis generiert, das den maximal zulässigen Wert überschreitet.

Diese Warnung kann durch Compileroptimierungen verursacht werden, die bei konstanter Arithmetik ausgeführt werden. Wenn Sie die Optimierung deaktivieren ([/od](../../build/reference/od-disable-debug.md)), können Sie diese Warnung gefahrlos ignorieren.

Im folgenden Beispiel wird C4056 generiert:

```cpp
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```