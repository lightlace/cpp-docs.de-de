---
title: Compilerwarnung (Stufe 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: f552a5d76d1a778cdf72cbe079138f609350ffb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511240"
---
# <a name="compiler-warning-level-4-c4221"></a>Compilerwarnung (Stufe 4) C4221

nicht dem Standard entsprechende Erweiterung: "Bezeichner": kann nicht mit der Adresse der automatischen Variablen initialisiert werden

Sie können mit den Standard-Microsoft-Erweiterungen (/ Ze), einen aggregierten Typ initialisieren (**Array**, `struct`, oder **Union**) mit der Adresse einer Variablen (automatisch).

## <a name="example"></a>Beispiel

```
// C4221.c
// compile with: /W4
struct S
{
   int *i;
};

void func()
{
   int j;
   struct S s1 = { &j };   // C4221
}

int main()
{
}
```

Diese Initialisierungen sind ungültig, ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).