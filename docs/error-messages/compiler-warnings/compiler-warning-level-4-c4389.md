---
title: Compilerwarnung (Stufe 4) C4389
ms.date: 11/04/2016
f1_keywords:
- c4389
helpviewer_keywords:
- C4389
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
ms.openlocfilehash: 7490218c0af61ef3b2346fc1bee9806d87d02294
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533392"
---
# <a name="compiler-warning-level-4-c4389"></a>Compilerwarnung (Stufe 4) C4389

'Operator': signed/unsigned-Konflikt

Ein Vorgang beteiligten mit und ohne Vorzeichen-Variablen. Dies kann zu einem Datenverlust führen.

Im folgende Beispiel wird die C4389 generiert:

```
// C4389.cpp
// compile with: /W4
#pragma warning(default: 4389)

int main()
{
   int a = 9;
   unsigned int b = 10;
   if (a == b)   // C4389
      return 0;
   else
      return 0;
};
```