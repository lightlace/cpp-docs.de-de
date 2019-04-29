---
title: Compilerwarnung (Stufe 1) C4167
ms.date: 11/04/2016
f1_keywords:
- C4167
helpviewer_keywords:
- C4167
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
ms.openlocfilehash: 8155fabacef4c9c9acc97b315f7267c23d032f12
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391711"
---
# <a name="compiler-warning-level-1-c4167"></a>Compilerwarnung (Stufe 1) C4167

Funktion: Nur als systeminterne Funktion verfügbar

Die **#pragma-Funktion** versucht zu erzwingen, dass der Compiler einen konventionellen Aufruf für eine Funktion verwendet, die in systeminterner Form verwendet werden muss. Das Pragma wird ignoriert.

Um diese Warnung zu vermeiden, entfernen Sie die **#pragma-Funhtion**.

## <a name="example"></a>Beispiel

```
// C4167.cpp
// compile with: /W1
#include <malloc.h>
#pragma function(_alloca )   // C4167: _alloca() is intrinsic only
int main(){}
```