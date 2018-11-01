---
title: Compilerfehler C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 66b7c0d61cbc8141b9ed3e5f6eb329b68eb00477
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609754"
---
# <a name="compiler-error-c2975"></a>Compilerfehler C2975

> "*Argument*": Ungültiges Vorlagenargument für "*Typ*", während der Kompilierung konstanter Ausdruck erwartet

Das Vorlagenargument entspricht nicht die Vorlagendeklaration; Ein konstanter Ausdruck sollte in spitzen Klammern angezeigt werden. Variablen werden als tatsächliche Vorlagenargumente nicht zulässig. Überprüfen Sie die Vorlagendefinition, um die richtigen Typen zu ermitteln.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2975 generiert, und es zeigt auch die richtige Verwendung:

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975 tritt auch bei Verwendung von &#95; &#95;Zeile&#95; &#95; als Konstante während der Kompilierung mit ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md). Eine mögliche Lösung bestünde mit Kompilieren ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) anstelle von **"/ Zi"**.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```