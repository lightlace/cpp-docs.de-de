---
title: Compilerwarnung (Stufe 2) C4056 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e069867d4aef749f9f6e42f46a34745d9e8aa62
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067506"
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