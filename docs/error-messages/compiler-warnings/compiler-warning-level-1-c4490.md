---
title: Compilerwarnung (Stufe 1) C4490
ms.date: 11/04/2016
f1_keywords:
- C4490
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
ms.openlocfilehash: 41fa124eed365b87b419a4019262c0c673399295
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966179"
---
# <a name="compiler-warning-level-1-c4490"></a>Compilerwarnung (Stufe 1) C4490

' override ': falsche Verwendung des Überschreibungsspezifizierers; "Function" stimmt nicht mit einer Basis Methode der Verweis Klasse

Ein Überschreibungsspezifizierer wurde falsch verwendet. Beispielsweise können Sie eine Schnittstellenfunktion nicht außer Kraft setzen, die Sie implementieren.

Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4490 generiert.

```cpp
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