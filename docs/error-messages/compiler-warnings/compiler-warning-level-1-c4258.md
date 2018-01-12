---
title: Compilerwarnung (Stufe 1) C4258 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4258
dev_langs: C++
helpviewer_keywords: C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 436ef3dd9984750885390a3974572b9d86bd7243
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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