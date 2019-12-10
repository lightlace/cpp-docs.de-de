---
title: Compilerwarnung (Stufe 3) C4522
ms.date: 11/04/2016
f1_keywords:
- C4522
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
ms.openlocfilehash: e791e490929daa4742a4db985f5a4f99f4db9d37
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992045"
---
# <a name="compiler-warning-level-3-c4522"></a>Compilerwarnung (Stufe 3) C4522

"Class": mehrere Zuweisungs Operatoren angegeben

Die-Klasse verfügt über mehrere Zuweisungs Operatoren eines einzelnen Typs. Diese Warnung dient nur zu Informationszwecken. die Konstruktoren können im Programm aufgerufen werden.

Verwenden Sie das [Warning](../../preprocessor/warning.md) -Pragma, um diese Warnung zu unterdrücken.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4522 generiert.

```cpp
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```
