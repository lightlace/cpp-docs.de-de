---
title: Compilerwarnung (Stufe 1) C4258 | Microsoft Docs
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
ms.openlocfilehash: 08a182ed592119fd52247737988810f9ca66b45c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4258"></a>Compilerwarnung (Stufe 1) C4258
'Variable': Definition von der for-Schleife ignoriert. die Definition des einschließenden Bereichs verwendet"  
  
 Unter ["/ Ze"](../../build/reference/za-ze-disable-language-extensions.md) und [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md), Variablen, die in definierten ein [für](../../cpp/for-statement-cpp.md) Schleife verlassen den Gültigkeitsbereich nach der **für** -Schleife beendet. Diese Warnung tritt auf, wenn eine Variable mit dem gleichen Namen wie die Schleifenvariable, jedoch in der umschließenden Schleife definiert erneut verwendet wird, im Bereich mit der **für** Schleife. Zum Beispiel:  
  
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