---
title: Compilerwarnung (Stufe 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: fa87c240472df2926753781f0f14cbd69752de00
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541926"
---
# <a name="compiler-warning-level-4-c4221"></a>Compilerwarnung (Stufe 4) C4221

nicht dem Standard entsprechende Erweiterung: "Bezeichner": kann nicht mit der Adresse der automatischen Variablen initialisiert werden.

Mit den standardmäßigen Microsoft-Erweiterungen (/Ze) können Sie einen aggregierten Typ (**Array**, `struct`oder **Union**) mit der Adresse einer lokalen (automatischen) Variablen initialisieren.

## <a name="example"></a>Beispiel

```c
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

Diese Initialisierungen sind unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ungültig.