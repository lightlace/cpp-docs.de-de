---
title: Compilerfehler C3414
ms.date: 11/04/2016
f1_keywords:
- C3414
helpviewer_keywords:
- C3414
ms.assetid: 715f5432-b509-4f8f-84f5-e1463bac490f
ms.openlocfilehash: 86ed40f31ae17724700e9d2c68950027d0eefb69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608990"
---
# <a name="compiler-error-c3414"></a>Compilerfehler C3414

'Member': importierte Memberfunktion kann nicht definiert werden

Ein Element wurde im Code definiert, die auch in einer referenzierten Assembly definiert ist.

Im folgende Beispiel wird die C3414 generiert:

```
// C3414a2.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

und anschließend:

```
// C3414b2.cpp
// compile with: /clr
#using <C3414a2.dll>

void MyClass::Test() {    // C3414
}

System::Object::Object() {    // C3414
}
```
