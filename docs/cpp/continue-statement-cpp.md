---
title: Fortfahren Anweisung (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: continue_cpp
dev_langs: C++
helpviewer_keywords: continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e4dd91489bfe22fca875f98110dadcb75def39d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="continue-statement-c"></a>continue-Anweisung (C++)
Erzwingt die Übertragung der Steuerung an den steuernden Ausdruck der kleinsten einschließenden [führen](../cpp/do-while-statement-cpp.md), [für](../cpp/for-statement-cpp.md), oder [während](../cpp/while-statement-cpp.md) Schleife.  
  
## <a name="syntax"></a>Syntax  
  
```  
continue;  
```  
  
## <a name="remarks"></a>Hinweise  
 Alle verbleibenden Anweisungen in der aktuellen Iteration werden nicht ausgeführt. Die nächste Iteration der Schleife wird wie folgt bestimmt:  
  
-   In einer `do`- oder `while`-Schleife wird die nächste Iteration mit einer erneuten Auswertung des steuernden Ausdrucks der `do`- oder der `while`-Anweisung begonnen.  
  
-   In einer `for`-Schleife (mit der Syntax `for`(`init-expr`; `cond-expr`; `loop-expr`)), wird die `loop-expr`-Klausel ausgeführt. Anschließend wird die `cond-expr`-Klausel neu ausgewertet und, je nach Ergebnis, wird die Schleife entweder beendet oder es tritt eine andere Iteration auf.  
  
 Das folgende Beispiel zeigt, wie die `continue`-Anweisung verwendet werden kann, um Abschnitte des Codes zu umgehen und die Iteration der nächsten Schleife zu starten.  
  
## <a name="example"></a>Beispiel  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
```Output  
before the continue  
before the continue  
before the continue  
after the do loop  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Sprunganweisungen](../cpp/jump-statements-cpp.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)