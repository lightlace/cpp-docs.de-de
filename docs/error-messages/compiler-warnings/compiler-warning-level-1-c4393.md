---
title: Compilerwarnung (Stufe 1) C4393
ms.date: 11/04/2016
f1_keywords:
- C4393
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
ms.openlocfilehash: 4226c8ecd41e890d70fa5741decae605d45b620f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768990"
---
# <a name="compiler-warning-level-1-c4393"></a>Compilerwarnung (Stufe 1) C4393

'Var': const hat keine Auswirkungen auf die literal-Datenmember; ignoriert

Ein [literal](../../extensions/literal-cpp-component-extensions.md) Datenmember wurde auch als const angegeben.  Da ein literal-Datenmember, const impliziert, müssen nicht Sie hinzuzufügende const der Deklaration.

Im folgende Beispiel wird die C4393 generiert:

```
// C4393.cpp
// compile with: /clr /W1 /c
ref struct Y1 {
   literal const int staticConst = 10;   // C4393
   literal int staticConst2 = 10;   // OK
};
```