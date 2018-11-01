---
title: Compilerwarnung (Stufe 1) C4273
ms.date: 11/04/2016
f1_keywords:
- C4273
helpviewer_keywords:
- C4273
ms.assetid: cc18611d-9454-40a4-ad73-69823d5888fb
ms.openlocfilehash: 4d00ed0113f9954e7400da24f37b51b9fdd247bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544325"
---
# <a name="compiler-warning-level-1-c4273"></a>Compilerwarnung (Stufe 1) C4273

"Function": Inkonsistente DLL-Bindung

Zwei Definitionen in einer Datei unterscheiden sich bei der Nutzung von [Dllimport](../../cpp/dllexport-dllimport.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4273 generiert.

```
// C4273.cpp
// compile with: /W1 /c
char __declspec(dllimport) c;
char c;   // C4273, delete this line or the line above to resolve
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4273 generiert.

```
// C4273_b.cpp
// compile with: /W1 /clr /c
#include <stdio.h>
extern "C" int printf_s(const char *, ...);   // C4273
```