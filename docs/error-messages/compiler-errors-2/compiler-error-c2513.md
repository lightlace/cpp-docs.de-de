---
title: Compilerfehler C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 093a5856fdcfa6311fcef93214672b035c91b4fc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746525"
---
# <a name="compiler-error-c2513"></a>Compilerfehler C2513

"Typ": keine Variable vor "=" deklariert

Der Typspezifizierer wird in der Deklaration ohne Variablen Bezeichner angezeigt.

Im folgenden Beispiel wird C2513 generiert:

```cpp
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

Dieser Fehler kann auch infolge einer für Visual Studio .NET 2003 abgeschlossenen compilerübereinstimmungs-Arbeit generiert werden: die Initialisierung einer TypeDef ist nicht mehr zulässig. Die Initialisierung einer TypeDef ist vom Standard nicht zulässig und generiert nun einen Compilerfehler.

```cpp
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

Eine Alternative besteht darin, `typedef` zu löschen, um eine Variable mit Aggregat Initialisiererliste zu definieren. Dies wird jedoch nicht empfohlen, da dadurch eine Variable mit dem gleichen Namen wie der Typ erstellt und der Typname ausgeblendet wird.
