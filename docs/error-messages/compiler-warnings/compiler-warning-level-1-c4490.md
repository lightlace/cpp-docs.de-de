---
title: Compilerwarnung (Stufe 1) C4490
ms.date: 11/04/2016
f1_keywords:
- C4490
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
ms.openlocfilehash: 89ee97a4efde6f2f9c57daf0ae769e5e12341913
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624340"
---
# <a name="compiler-warning-level-1-c4490"></a>Compilerwarnung (Stufe 1) C4490

"override": falsche Verwendung des Überschreibungsspezifizierers; 'Funktion' stimmt nicht mit dem eine Klassenmethode Basismethode der Verweisklasse überein.

Ein Überschreibungsspezifizierer wurde falsch verwendet. Z. B. eine Funktion der Schnittstelle nicht überschreiben, Sie implementieren.

Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4490 generiert.

```
// C4490.cpp
// compile with: /clr /c /W1

interface struct IFace {
   void Test();
};

ref struct Class1 : public IFace {
   virtual void Test() override {}   // C4490
   // try the following line instead
   // virtual void Test() {}
};
```