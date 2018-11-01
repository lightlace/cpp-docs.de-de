---
title: Compilerfehler C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: e41ea1dbe1f2bd47f9b557d502ec95bcecb1e2a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428262"
---
# <a name="compiler-error-c3887"></a>Compilerfehler C3887

'Var': der Initialisierer für ein literal-Datenmembers muss ein konstanter Ausdruck sein

Ein [literal](../../windows/literal-cpp-component-extensions.md) -Datenmember kann nur mit einem konstanten Ausdruck initialisiert werden.

Im folgende Beispiel wird die C3887 generiert:

```
// C3887.cpp
// compile with: /clr
ref struct Y1 {
   static int i = 9;
   literal
   int staticConst = i;   // C3887
};
```

Mögliche Lösung:

```
// C3887b.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   int staticConst = 9;
};
```