---
title: Compilerwarnung C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: 896fca6c6b257c90ccdf813a9c6cb6bc27ad9e96
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623609"
---
# <a name="compiler-warning-c4485"></a>Compilerwarnung C4485

"override_function": stimmt mit der "base_class_function"-Basis Methode der Verweis Klasse überein, ist jedoch nicht als "New" oder "override" markiert. "New" (und "Virtual") wird angenommen.

Ein-Accessor überschreibt, mit oder ohne das `virtual`-Schlüsselwort, eine Basisklassen-Accessorfunktion, aber der `override`-oder `new`-Spezifizierer war nicht Teil der über schreibenden Funktions Signatur. Fügen Sie den `new` oder `override` Spezifizierer hinzu, um diese Warnung zu beheben.

Weitere Informationen finden Sie unter [override](../../extensions/override-cpp-component-extensions.md) und [New (neuer Slot in Vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) .

C4485 wird immer als Fehler ausgegeben. Verwenden Sie das [Warning](../../preprocessor/warning.md) -Pragma, um C4485 zu unterdrücken.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4485 generiert.

```cpp
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```