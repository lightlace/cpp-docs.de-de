---
title: Compilerfehler C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 13840246a5dc6a1c1bdbcb55dc47f212ee353d81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165215"
---
# <a name="compiler-error-c2513"></a>Compilerfehler C2513

'type' : no variable declared before '='

Der Typspezifizierer wird angezeigt, in der Deklaration keinen Variablenbezeichner.

Im folgende Beispiel wird die C2513 generiert:

```
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Compiler für Visual Studio .NET 2003 erledigt generiert werden: Initialisierung einer Typedef, die nicht mehr zulässig. Die Initialisierung einer TypeDef ist gemäß dem Standard nicht zulässig und wird nun ein Compilerfehler generiert.

```
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

Eine Alternative wäre löschen `typedef` zum Definieren einer Variablen mit aggregierten Initialisiererliste, aber dies werden nicht empfohlen, da wird und erstellen Sie eine Variable mit dem gleichen Namen wie der Typ der Typname ausblenden.