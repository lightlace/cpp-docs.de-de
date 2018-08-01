---
title: continue-Anweisung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0ab1e052b3e6d843813c33e5444fc3c08796d00
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402090"
---
# <a name="continue-statement-c"></a>continue-Anweisung (C++)
Erzwingt die Übertragung der Steuerung an den steuernden Ausdruck der kleinsten einschließenden [führen](../cpp/do-while-statement-cpp.md), [für](../cpp/for-statement-cpp.md), oder [während](../cpp/while-statement-cpp.md) Schleife.  
  
## <a name="syntax"></a>Syntax  
  
```  
continue;  
```  
  
## <a name="remarks"></a>Hinweise  
 Alle verbleibenden Anweisungen in der aktuellen Iteration werden nicht ausgeführt. Die nächste Iteration der Schleife wird wie folgt bestimmt:  
  
-   In einer **führen** oder **während** Schleife, die nächste Iteration beginnt mit einer erneuten Auswertung des steuernden Ausdrucks die **führen** oder **während** Anweisung.  
  
-   In einem **für** Schleife (mit der Syntax `for`(`init-expr`; `cond-expr`; `loop-expr`)), wird die `loop-expr` -Klausel ausgeführt wird. Anschließend wird die `cond-expr`-Klausel neu ausgewertet und, je nach Ergebnis, wird die Schleife entweder beendet oder es tritt eine andere Iteration auf.  
  
 Das folgende Beispiel zeigt die **weiterhin** Anweisung kann verwendet werden, um Abschnitte des Codes zu umgehen und die nächste Iteration einer Schleife zu beginnen.  
  
## <a name="example"></a>Beispiel  
  
```cpp 
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