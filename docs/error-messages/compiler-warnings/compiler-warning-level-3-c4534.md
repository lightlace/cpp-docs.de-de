---
title: Compilerwarnung (Stufe 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: a2af04502082f7fb30d59af5e6434161227c6d30
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437267"
---
# <a name="compiler-warning-level-3-c4534"></a>Compilerwarnung (Stufe 3) C4534

'Konstruktor' werden nicht auf einen Standardkonstruktor für Klasse 'Klasse' aufgrund von das Standardargument

Eine nicht verwaltete Klasse kann einen Konstruktor mit Parametern, die Standardwerte festgelegt wurden und der Compiler wird dies als den Standardkonstruktor verwenden. Eine Klasse mit markiert die `value` Schlüsselwort nicht verwendet einen Konstruktor mit standardmäßigen Werten für die Parameter als einen standardmäßigen Konstruktor.

Weitere Informationen finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md).

Im folgende Beispiel wird die C4534 generiert:

```
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