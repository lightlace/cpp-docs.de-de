---
title: Compilerwarnung (Stufe 3) C4636
ms.date: 11/04/2016
f1_keywords:
- C4636
helpviewer_keywords:
- C4636
ms.assetid: 59112a0f-850f-41c6-bd84-8ae8dc84706a
ms.openlocfilehash: 7327189a61e2545bb6003cd95e1ddb116f9f7c94
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542232"
---
# <a name="compiler-warning-level-3-c4636"></a>Compilerwarnung (Stufe 3) C4636

Auf 'construct' angewendeter XML-Dokumentkommentar: Für das Tag ist ein nicht leeres Attribut erforderlich.

Ein Tag, wie etwa `cref`, wies keinen Wert auf.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4636 generiert:

```
// C4636.cpp
// compile with: /clr /doc /W3 /c
/// <see cref=''/>
// /// <see cref='System::Exception'/>
ref struct A {   // C4636
   void f(int);
};

// OK
/// <see cref='System::Exception'/>
ref struct B {
   void f(int);
};
```