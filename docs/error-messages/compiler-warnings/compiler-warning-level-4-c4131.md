---
title: Compilerwarnung (Stufe 4) C4131
ms.date: 11/04/2016
f1_keywords:
- C4131
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
ms.openlocfilehash: 24872bb0b42de77dde358dc29f99826b41638628
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516054"
---
# <a name="compiler-warning-level-4-c4131"></a>Compilerwarnung (Stufe 4) C4131

"function": Verwendet Deklarator für altes Format

Die angegebene Funktionsdeklaration weist keine Prototypform auf.

Funktionsdeklarationen im alten Format sollten in die Prototypform konvertiert werden.

Im folgenden Beispiel wird eine Funktionsdeklaration im alten Stil veranschaulicht:

```
// C4131.c
// compile with: /W4 /c
void addrec( name, id ) // C4131 expected
char *name;
int id;
{ }
```

Im folgenden Beispiel wird eine Prototypform veranschaulicht:

```
void addrec( char *name, int id )
{ }
```