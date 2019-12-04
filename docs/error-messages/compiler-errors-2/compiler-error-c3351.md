---
title: Compilerfehler C3351
ms.date: 11/04/2016
f1_keywords:
- C3351
helpviewer_keywords:
- C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
ms.openlocfilehash: d93d6b08268aa8d6a7a7ad2e2086f4799417bbb4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737464"
---
# <a name="compiler-error-c3351"></a>Compilerfehler C3351

'Object': Delegatkonstruktor: Das zweite Argument muss eine Adresse einer statischen Memberfunktion oder einer globalen Funktion sein.

Der Compiler hat die Adresse einer Funktion erwartet, die als `static`deklariert ist.

Im folgenden Beispiel wird C3351 generiert:

```cpp
// C3351a.cpp
// compile with: /clr
delegate int D(int, int);

ref class C {
public:
   int mf(int, int) {
      return 1;
   }

   static int mf2(int, int) {
      return 1;
   }
};

int main() {
   System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351
   System::Delegate ^pD2 = gcnew D(&C::mf2);
}
```
