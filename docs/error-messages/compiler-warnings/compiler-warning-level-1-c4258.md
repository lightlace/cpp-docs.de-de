---
title: Compilerwarnung (Stufe 1) C4258 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4258
dev_langs:
- C++
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4d9aacd6e3681a1eb42073df8a13d7ce72c5634
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083534"
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