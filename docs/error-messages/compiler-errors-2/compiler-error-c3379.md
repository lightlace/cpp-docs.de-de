---
title: Compilerfehler C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 9d99214f3ad7e7db1edc215d94c98e9cf9ec4ca2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742898"
---
# <a name="compiler-error-c3379"></a>Compilerfehler C3379

"Class": eine in eine Klasse eingefügte Klasse kann keinen Assemblyzugriffsspezifizierer als Teil der Deklaration

Bei Anwendung auf einen verwalteten Typ, wie z. b. eine Klasse oder Struktur, geben die [öffentlichen](../../cpp/public-cpp.md) und [privaten](../../cpp/private-cpp.md) Schlüsselwörter an, ob die Klasse über Assemblymetadaten verfügbar gemacht wird. `public` oder `private` kann nicht auf eine nicht auf eine-Klasse festgelegt werden, die den Assemblyzugriff der einschließenden Klasse erbt.

Bei Verwendung mit [/CLR](../../build/reference/clr-common-language-runtime-compilation.md)geben die Schlüsselwörter `ref` und `value` an, dass eine Klasse verwaltet wird (siehe [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Im folgenden Beispiel wird C3379 generiert:

```cpp
// C3379a.cpp
// compile with: /clr
using namespace System;

public ref class A {
public:
   static int i = 9;

   public ref class BA {   // C3379
   // try the following line instead
   // ref class BA {
   public:
      static int ii = 8;
   };
};

int main() {

   A^ myA = gcnew A;
   Console::WriteLine(myA->i);

   A::BA^ myBA = gcnew A::BA;
   Console::WriteLine(myBA->ii);
}
```
