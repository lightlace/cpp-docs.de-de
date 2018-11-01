---
title: Compilerfehler C2808
ms.date: 11/04/2016
f1_keywords:
- C2808
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
ms.openlocfilehash: 7b40a81748748a7566a8c1e6add84121f8925895
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572012"
---
# <a name="compiler-error-c2808"></a>Compilerfehler C2808

Der unäre 'Operator Operator' hat zu viele formale Parameter

Der unäre Operator verfügt über eine Parameterliste.

Im folgende Beispiel wird die C2808 generiert:

```
// C2808.cpp
// compile with: /c
class X {
public:
   X operator! ( X );   // C2808 nonvoid parameter list
   X operator! ( void );   // OK
};

```