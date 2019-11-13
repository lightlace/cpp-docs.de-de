---
title: Compilerwarnung (Stufe 1) C4669
ms.date: 11/04/2016
f1_keywords:
- C4669
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
ms.openlocfilehash: 58f7150caeb3e06ba400a08c6e484f677a8deff9
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051387"
---
# <a name="compiler-warning-level-1-c4669"></a>Compilerwarnung (Stufe 1) C4669

"Umwandlung" : Unsichere Konvertierung: "Klasse" ist ein verwaltetes Objekt oder ein Objekt mit dem Typ WinRT.

Eine Umwandlung beinhaltet eine Windows-Runtime oder einen verwalteten Typ. Der Compiler schließt die Umwandlung anhand einer bitweisen Kopie des einen Zeiger zu einem anderen ab, bietet jedoch keine weiteren Überprüfungen. Um diese Warnung zu vermeiden, sollten Sie keine Klassen mit verwalteten Members oder Windows-Runtime-Typen umwandeln.

Im folgenden Beispiel wird C4669 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C4669.cpp
// compile with: /clr /W1
ref struct A {
   int i;
   Object ^ pObj;   // remove the managed member to fix the warning
};

ref struct B {
   int j;
};

int main() {
   A ^ a = gcnew A;
   B ^ b = reinterpret_cast<B ^>(a);   // C4669
}
```