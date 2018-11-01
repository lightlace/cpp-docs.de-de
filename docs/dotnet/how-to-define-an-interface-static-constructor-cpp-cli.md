---
title: 'Gewusst wie: Definieren eines statischen Schnittstellenkonstruktors (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [C++]
- static constructors, interface
- interface static constructor
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
ms.openlocfilehash: 0617454e0957dccc7e28a5172a40273b5d93bede
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566386"
---
# <a name="how-to-define-an-interface-static-constructor-ccli"></a>Gewusst wie: Definieren eines statischen Schnittstellenkonstruktors (C++/CLI)

Eine Schnittstelle kann einen statischen Konstruktor besitzen, die zum Initialisieren von statischen Datenmembern verwendet werden kann.  Ein statischer Konstruktor wird höchstens einmal aufgerufen werden und wird vor dem beim ersten Zugriff auf Member einer statischen Schnittstelle aufgerufen werden.

## <a name="example"></a>Beispiel

```
// mcppv2_interface_class2.cpp
// compile with: /clr
using namespace System;

interface struct MyInterface {
   static int i;
   static void Test() {
      Console::WriteLine(i);
   }

   static MyInterface() {
      Console::WriteLine("in MyInterface static constructor");
      i = 99;
   }
};

ref class MyClass : public MyInterface {};

int main() {
   MyInterface::Test();
   MyClass::MyInterface::Test();

   MyInterface ^ mi = gcnew MyClass;
   mi->Test();
}
```

```Output
in MyInterface static constructor
99
99
99
```

## <a name="see-also"></a>Siehe auch

[Schnittstellenklasse](../windows/interface-class-cpp-component-extensions.md)