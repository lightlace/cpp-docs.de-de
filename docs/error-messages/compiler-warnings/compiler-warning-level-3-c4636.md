---
title: Compilerwarnung (Stufe 3) C4636
ms.date: 11/04/2016
f1_keywords:
- C4636
helpviewer_keywords:
- C4636
ms.assetid: 59112a0f-850f-41c6-bd84-8ae8dc84706a
ms.openlocfilehash: 7327189a61e2545bb6003cd95e1ddb116f9f7c94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401708"
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