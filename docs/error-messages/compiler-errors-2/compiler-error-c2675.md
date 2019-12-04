---
title: Compilerfehler C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: 0b7b81ce7314fbad02d6873403fc5cf1bdd54709
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760373"
---
# <a name="compiler-error-c2675"></a>Compilerfehler C2675

unärer ' Operator ': ' type ' definiert diesen Operator oder eine Konvertierung in einen Typ, der für den vordefinierten Operator akzeptabel ist.

C2675 kann auch auftreten, wenn ein unärer Operator verwendet wird, und der Typ definiert nicht den Operator oder eine Konvertierung in einen Typ, der für den vordefinierten Operator akzeptabel ist. Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2675 generiert.

```cpp
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```
