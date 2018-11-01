---
title: Compilerwarnung (Stufe 3) C4521
ms.date: 11/04/2016
f1_keywords:
- C4521
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
ms.openlocfilehash: 887526810f7e65280adcde422ef871a67ccdde1f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591810"
---
# <a name="compiler-warning-level-3-c4521"></a>Compilerwarnung (Stufe 3) C4521

'Klasse': Mehrere Kopierkonstruktoren angegeben

Die Klasse verfügt über mehrere Kopierkonstruktoren eines einzelnen Typs. Diese Warnung dient nur zu Informationszwecken; die Konstruktoren, die in Ihrem Programm können aufgerufen werden.

Verwenden der [Warnung](../../preprocessor/warning.md) Pragma, um diese Warnung unterdrücken.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4521 generiert.

```
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