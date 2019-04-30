---
title: Compilerfehler C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: 85434cb8daba0db82843c09e2d1bb09d98960272
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344500"
---
# <a name="compiler-error-c3887"></a>Compilerfehler C3887

'Var': der Initialisierer für ein literal-Datenmembers muss ein konstanter Ausdruck sein

Ein [literal](../../extensions/literal-cpp-component-extensions.md) -Datenmember kann nur mit einem konstanten Ausdruck initialisiert werden.

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