---
title: Compilerwarnung (Stufe 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 2e617b18f2c7ed3b51d25eb44101629bbadcef9d
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189089"
---
# <a name="compiler-warning-level-3-c4534"></a>Compilerwarnung (Stufe 3) C4534

"Konstruktor" ist aufgrund des Standard Arguments kein Standardkonstruktor für die Klasse "Class".

Eine nicht verwaltete Klasse kann über einen Konstruktor mit Parametern verfügen, die über Standardwerte verfügen, und der Compiler verwendet diese als Standardkonstruktor. Eine mit dem `value`-Schlüsselwort markierte Klasse verwendet keinen Konstruktor mit Standardwerten für die Parameter als Standardkonstruktor.

Weitere Informationen finden Sie unter [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md).

Im folgenden Beispiel wird C4534 generiert:

```cpp
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```