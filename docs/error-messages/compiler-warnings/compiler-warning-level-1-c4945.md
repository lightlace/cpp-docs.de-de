---
title: Compilerwarnung (Stufe 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: 62dfbaed28f1afcdedb41d83158dfe4e8e0f61b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653855"
---
# <a name="compiler-warning-level-1-c4945"></a>Compilerwarnung (Stufe 1) C4945

'Symbol': Symbol aus "assembly2" kann nicht importiert: 'Symbol' wurde bereits von einer anderen Assembly 'assembly1' importiert

Ein Symbol aus einer referenzierten Assembly importiert wurden, aber das Symbol bereits aus einer anderen referenzierten Assembly importiert wurden. Entweder eine der Assemblys verweisen, und nicht der Symbolname in eine der Assemblys geändert.

In den folgenden Beispielen wird C4945 generiert:

```
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Und dann

```
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Und dann

```
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```