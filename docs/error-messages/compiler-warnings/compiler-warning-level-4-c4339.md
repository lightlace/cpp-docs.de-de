---
title: Compilerwarnung (Stufe 4) C4339
ms.date: 11/04/2016
f1_keywords:
- C4339
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
ms.openlocfilehash: bc9d335b3a09f7953a12b388d5bb40cc4d433969
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567764"
---
# <a name="compiler-warning-level-4-c4339"></a>Compilerwarnung (Stufe 4) C4339

'Typ' : Die Verwendung eines undefinierten Typs wurde in WinRT oder CLR-Metadaten entdeckt. Das Verwenden dieses Typs führt möglicherweise zu einer Laufzeitausnahme.

Ein Typ wurde nicht im Code definiert, der für die Windows-Runtime oder der Common Language Runtime kompiliert wurde. Definieren Sie den Typ, um eine mögliche Laufzeitausnahme zu vermeiden.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4339 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C4339.cpp
// compile with: /W4 /clr /c
// C4339 expected
#pragma warning(default : 4339)

// Delete the following line to resolve.
class A;

// Uncomment the following line to resolve.
// class A{};

class X {
public:
   X() {}

   virtual A *mf() {
      return 0;
   }
};

X * f() {
   return new X();
}
```