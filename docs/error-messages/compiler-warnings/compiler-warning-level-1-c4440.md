---
title: Compilerwarnung (Stufe 1) C4440
ms.date: 11/04/2016
f1_keywords:
- C4440
helpviewer_keywords:
- C4440
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
ms.openlocfilehash: ccd7c14cbd078d4740795d25ad772bdc78840a60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660054"
---
# <a name="compiler-warning-level-1-c4440"></a>Compilerwarnung (Stufe 1) C4440

Neudefinition der Aufrufkonvention von 'calling_convention1', 'calling_convention2 'wurde ignoriert

Ein Versuch, ändern die Aufrufkonvention wurde ignoriert.

Im folgende Beispiel wird die C4440 generiert:

```
// C4440.cpp
// compile with: /W1 /LD /clr
typedef void __clrcall F();
typedef F __cdecl *PFV;   // C4440
```