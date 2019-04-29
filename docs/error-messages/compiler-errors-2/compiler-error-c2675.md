---
title: Compilerfehler C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: aea79509d0e1ae5c31fcf0cf369c28af39a21154
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367927"
---
# <a name="compiler-error-c2675"></a>Compilerfehler C2675

unärer 'Operator Operator': 'Typ' definiert nicht diesen Operator oder eine Konvertierung in einen geeigneten Typ für den vordefinierten Operator

C2675 kann auch auftreten, wenn einen unäroperator, und der Typ definiert nicht den Operator oder eine Konvertierung in einen geeigneten Typ für den vordefinierten Operator. Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2675 generiert.

```
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