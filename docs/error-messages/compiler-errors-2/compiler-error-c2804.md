---
title: Compilerfehler C2804 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2804
dev_langs:
- C++
helpviewer_keywords:
- C2804
ms.assetid: b066e563-cca4-450c-8ba7-3b0d7a89f3ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987176753d9c9dcd21ddbe06ef2e5b59c24dd79b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036942"
---
# <a name="compiler-error-c2804"></a>Compilerfehler C2804

Binärer Operator "Operator" hat zu viele Parameter

Die überladene binäre Operator-Memberfunktion wird mit mehr als einem Parameter deklariert. Der erste Parameter für Operanden einer binären Operator-Memberfunktion, deren Typ des Operators ist einschließender Typ ist, wird impliziert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2804 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2804.cpp
// compile by using: cl /c /W4 C2804.cpp
class X {
public:
   X& operator+= (const X &left, const X &right);   // C2804
   X& operator+= (const X &right);   // OK - left operand implicitly *this
};

int main() {
   X x, y;
   x += y;   // equivalent to x.operator+=(y)
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2804 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2804_2.cpp
// compile with: /clr /c
ref struct Y {
   Y^ operator +(Y^ hY, int i);   // C2804
   static Y^ operator +(Y^ hY, int i);   // OK
   Y^ operator +(int i);   // OK
};
```