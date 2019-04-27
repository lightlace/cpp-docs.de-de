---
title: Compilerwarnung (Stufe 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4610
helpviewer_keywords:
- C4610
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
ms.openlocfilehash: ce671552083f4e6b055c52e7387d3a95e7d47c0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220579"
---
# <a name="compiler-warning-level-4-c4610"></a>Compilerwarnung (Stufe 1) C4600

'Klasse'-Objekt kann niemals instanziiert werden-benutzerdefinierter Konstruktor erforderlich-

Die Klasse hat keine benutzerdefinierten oder Standardkonstruktoren. Es ist keine Instanziierung ausgeführt. Im folgende Beispiel wird die C4610 generiert:

```
// C4610.cpp
// compile with: /W4
struct A {
   int &j;

   A& A::operator=( const A& );
};   // C4610

/* use this structure definition to resolve the warning
struct B {
   int &k;

   B(int i = 0) : k(i) {
   }

   B& B::operator=( const B& );
} b;
*/

int main() {
}
```