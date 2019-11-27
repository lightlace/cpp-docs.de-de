---
title: Compilerwarnung (Stufe 3) C4521
ms.date: 11/04/2016
f1_keywords:
- C4521
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
ms.openlocfilehash: 362fd3c14037fa62ab73c928a45eaf7808de66bc
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189365"
---
# <a name="compiler-warning-level-3-c4521"></a>Compilerwarnung (Stufe 3) C4521

"Class": mehrere Kopierkonstruktoren angegeben

Die-Klasse verfügt über mehrere Kopierkonstruktoren eines einzelnen Typs. Diese Warnung dient nur zu Informationszwecken. die Konstruktoren können im Programm aufgerufen werden.

Verwenden Sie das [Warning](../../preprocessor/warning.md) -Pragma, um diese Warnung zu unterdrücken.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4521 generiert.

```cpp
// C4521.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A() { cout << "A's default constructor" << endl; }
   A( A &o ) { cout << "A&" << endl; }
   A( const A &co ) { cout << "const A&" << endl; }   // C4521
};

int main() {
   A o1;         // Calls default constructor.
   A o2( o1 );   // Calls A( A& ).
   const A o3;   // Calls default constructor.
   A o4( o3 );   // Calls A( const A& ).
}
```