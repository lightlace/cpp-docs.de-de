---
title: Compilerwarnung (Stufe 1) C4163
ms.date: 11/04/2016
f1_keywords:
- C4163
helpviewer_keywords:
- C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
ms.openlocfilehash: 737cf7ad00bfefd429792eed3f730844789e0c02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391763"
---
# <a name="compiler-warning-level-1-c4163"></a>Compilerwarnung (Stufe 1) C4163

'bezeichner': nicht als intrinsische Funktion verfügbar

Die angegebene Funktion kann nicht als [intrinsische](../../preprocessor/intrinsic.md) Funktion verwendet werden. Der Compiler ignoriert den ungültigen Funktionsnamen.

Im folgenden Beispiel wird C4163 generiert.

```
// C4163.cpp
// compile with: /W1 /LD
#include <math.h>
#pragma intrinsic(mysin)   // C4163
// try the following line instead
// #pragma intrinsic(sin)
```