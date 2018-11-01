---
title: Compilerwarnung (Stufe 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: a3ce4c81a86920baddfc1b277df0236a96254be4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478267"
---
# <a name="compiler-warning-level-1-c4258"></a>Compilerwarnung (Stufe 1) C4258

'Variable': Definition von der for-Schleife ignoriert. die Definition des umschließenden Gültigkeitsbereich verwendet"

Unter [/Ze](../../build/reference/za-ze-disable-language-extensions.md) und [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md), in der definierten Variablen ein [für](../../cpp/for-statement-cpp.md) Schleife verlassen den Gültigkeitsbereich nach Beenden der **für** Schleife. Diese Warnung tritt auf, wenn eine Variable mit dem gleichen Namen wie die Schleifenvariable, jedoch in der einschließenden Schleife definiert erneut verwendet wird, im Bereich mit der **für** Schleife. Zum Beispiel:

```
// C4258.cpp
// compile with: /Zc:forScope /W1
int main()
{
   int i;
   {
      for (int i =0; i < 1; i++)
         ;
      i = 20;   // C4258 i (in for loop) has gone out of scope
   }
}
```