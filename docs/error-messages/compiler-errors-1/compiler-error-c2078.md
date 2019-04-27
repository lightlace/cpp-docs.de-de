---
title: Compilerfehler C2078
ms.date: 11/04/2016
f1_keywords:
- C2078
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
ms.openlocfilehash: a800a6efa6e02f323b4b6597f1aa983f13674e83
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182807"
---
# <a name="compiler-error-c2078"></a>Compilerfehler C2078

Zu viele Initialisierungen

Die Anzahl der Initialisierungen überschreitet die Anzahl der zu initialisierenden Objekte.

Wenn die innere Klammern aus der Initialisiererliste entfernt werden, kann der Compiler die richtige Zuweisung der Initialisierer für Objekte und interne Objekte ableiten. Durch vollständige Klammern werden Mehrdeutigkeiten beseitigt und somit Ergebnisse in der richtigen Zuweisung angezeigt. Teilweise Klammern lösen möglicherweise C2087 aufgrund von Mehrdeutigkeit in der Zuweisung des Initialisierers für Objekte aus.

Im folgenden Beispiel wird C2078 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2078.cpp
// Compile by using: cl /c /W4 C2078.cpp
struct S {
   struct {
      int x, y;
   } z[2];
};

int main() {
   int d[2] = {1, 2, 3};   // C2078
   int e[2] = {1, 2};      // OK

   char a[] = {"a", "b"};  // C2078
   char *b[] = {"a", "b"}; // OK
   char c[] = {'a', 'b'};  // OK

   S s1{1, 2, 3, 4};       // OK
   S s2{{1, 2}, {3, 4}};   // C2078
   S s3{{1, 2, 3, 4}};     // OK
   S s4{{{1, 2}, {3, 4}}}; // OK
}
```