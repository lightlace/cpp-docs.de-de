---
title: Compilerwarnung (Stufe 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 59c66f2f7dcbd1e20463df613b1b7deae6a1c349
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349866"
---
# <a name="compiler-warning-level-2-c4056"></a>Compilerwarnung (Stufe 2) C4056

Überlauf bei Gleitkommakonstanten-Arithmetik

Gleitkommakonstanten-Arithmetik generiert ein Ergebnis, das den maximalen zulässigen Wert überschreitet.

Diese Warnung kann durch compileroptimierungen, die während arithmetischer Auswertung einer Konstanten verursacht werden. Sie können diese Warnung gefahrlos ignorieren, wenn er beendet wird, wenn Sie die Optimierung zu deaktivieren ([/Od](../../build/reference/od-disable-debug.md)).

Im folgende Beispiel wird die C4056 generiert:

```
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```