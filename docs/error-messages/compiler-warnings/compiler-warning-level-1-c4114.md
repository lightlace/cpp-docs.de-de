---
title: Compilerwarnung (Stufe 1) C4114 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4114
dev_langs:
- C++
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8d67148c2b9fb22c90013905eb246bf8d3bdf75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067564"
---
# <a name="compiler-warning-level-1-c4114"></a>Compilerwarnung (Stufe 1) C4114

Der gleiche Typqualifizierer wurde mehrmals verwendet

Eine Typdeklaration oder-Definition verwendet ein Typqualifizierer (**const**, **flüchtige**, **signiert**, oder **ohne Vorzeichen**) mehr als einmal. Dies bewirkt, dass eine Warnung mit Microsoft-Erweiterungen (/ Ze) und ANSI-Kompatibilität (/ Za).

Im folgende Beispiel wird die C4114 generiert:

```
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

Im folgende Beispiel wird die C4114 generiert:

```
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
