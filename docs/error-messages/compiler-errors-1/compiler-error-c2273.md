---
title: Compilerfehler C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: f2ed5c49a9f8243fd5c9c302caf2876493c26bc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388942"
---
# <a name="compiler-error-c2273"></a>Compilerfehler C2273

"Type": unzulässig auf der rechten Seite des Operators "->"

Ein Typ wird als der Rechte Operand des eine `->` Operator.

Dieser Fehler kann verursacht werden, indem Sie versuchen, eine benutzerdefinierte typkonvertierung zugreifen. Verwenden Sie das Schlüsselwort `operator` zwischen -> und `type`.

Im folgende Beispiel wird die C2273 generiert:

```
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```