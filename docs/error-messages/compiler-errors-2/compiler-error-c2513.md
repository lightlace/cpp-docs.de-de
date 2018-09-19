---
title: Compilerfehler C2513 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82df537e49ca17140d70977486314f43a072022d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045431"
---
# <a name="compiler-error-c2513"></a>Compilerfehler C2513

'Typ': keine Variable vor "=" deklariert

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