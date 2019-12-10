---
title: Compilerwarnung (Stufe 4) C4339
ms.date: 11/04/2016
f1_keywords:
- C4339
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
ms.openlocfilehash: e7c3f6f3a2cb9da9857d8336d24d57caf8114850
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991204"
---
# <a name="compiler-warning-level-4-c4339"></a>Compilerwarnung (Stufe 4) C4339

'Typ' : Die Verwendung eines undefinierten Typs wurde in WinRT oder CLR-Metadaten entdeckt. Das Verwenden dieses Typs führt möglicherweise zu einer Laufzeitausnahme.

Ein Typ wurde nicht im Code definiert, der für die Windows-Runtime oder der Common Language Runtime kompiliert wurde. Definieren Sie den Typ, um eine mögliche Laufzeitausnahme zu vermeiden.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4339 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
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
