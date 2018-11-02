---
title: Compilerwarnung (Stufe 4) C4510
ms.date: 11/04/2016
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: 80183e9f7ef17cbc37592f36eb8db1df2be94827
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539060"
---
# <a name="compiler-warning-level-4-c4510"></a>Compilerwarnung (Stufe 4) C4510

'Klasse': Standard-Konstruktor konnte nicht generiert werden

Kann nicht generiert der Compiler einen Standardkonstruktor für die angegebene Klasse aus, und keinen benutzerdefinierten Konstruktor erstellt wurde. Sie werden nicht auf Objekte dieses Typs erstellen können.

Es gibt mehrere Situationen, die verhindern, dass den Compiler generiert einen Standard-Konstruktor, einschließlich:

- Ein Datenmember.

- Ein Datenmember, der ein Verweis ist.

Sie müssen einen benutzerdefinierten Standardkonstruktor für die Klasse zu erstellen, die diese Member initialisiert.

Im folgende Beispiel wird die C4510 generiert:

```
// C4510.cpp
// compile with: /W4
struct A {
   const int i;
   int &j;
   A& operator=( const A& ); // C4510 expected
   // uncomment the following line to resolve this C4510
   // A(int ii, int &jj) : i(ii), j(jj) {}
};   // C4510

int main() {
}
```