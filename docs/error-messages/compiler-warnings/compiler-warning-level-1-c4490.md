---
title: Compilerwarnung (Stufe 1) C4490
ms.date: 11/04/2016
f1_keywords:
- C4490
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
ms.openlocfilehash: bf51994c210bd751e0d29bec169dfc4366784486
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779182"
---
# <a name="compiler-warning-level-1-c4490"></a>Compilerwarnung (Stufe 1) C4490

"override": falsche Verwendung des Überschreibungsspezifizierers; 'Funktion' stimmt nicht mit dem eine Klassenmethode Basismethode der Verweisklasse überein.

Ein Überschreibungsspezifizierer wurde falsch verwendet. Z. B. eine Funktion der Schnittstelle nicht überschreiben, Sie implementieren.

Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../extensions/override-specifiers-cpp-component-extensions.md).

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