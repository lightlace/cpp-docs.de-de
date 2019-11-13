---
title: Compilerwarnung (Stufe 1) C4486
ms.date: 11/04/2016
f1_keywords:
- C4486
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
ms.openlocfilehash: 4c92c23af4aeb6a18c812517cfef9fa00d15dfcb
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965393"
---
# <a name="compiler-warning-level-1-c4486"></a>Compilerwarnung (Stufe 1) C4486

"Function": eine private virtuelle Methode einer Verweis Klasse oder einer Werte Klasse sollte als "versiegelt" markiert werden.

Da auf eine private virtuelle Member-Funktion einer verwalteten Klasse oder Struktur nicht zugegriffen werden kann oder diese überschrieben werden kann, sollte Sie als [versiegelt](../../extensions/sealed-cpp-component-extensions.md)gekennzeichnet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4486 generiert.

```cpp
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine mögliche Verwendung einer privaten versiegelten virtuellen Funktion.

```cpp
// C4486_b.cpp
// compile with: /clr /c
ref class B {};

ref class D : B {};

interface class I {
   B^ mf();
};

ref class E : I {
private:
   virtual B^ g() sealed = I::mf {
      return gcnew B;
   }

public:
   virtual D^ mf() {
      return gcnew D;
   }
};
```