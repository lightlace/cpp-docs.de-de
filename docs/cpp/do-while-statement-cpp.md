---
title: Führen Sie-while-Anweisung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- do_cpp
dev_langs:
- C++
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2de180d58c31f4bd6c8b15eb69076b99f8b57b0
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943655"
---
# <a name="do-while-statement-c"></a>do-while-Anweisung (C++)
Führt eine *Anweisung* solange wiederholt, bis die angegebene beendigungsbedingung (der *Ausdruck*) zu NULL ausgewertet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
do  
   statement  
while ( expression ) ;  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Test der beendigungsbedingung wird nach jeder Ausführung der Schleife wird. aus diesem Grund eine **sind – während** Schleife ausgeführt wird, einmal oder mehrmals, abhängig vom Wert des beendigungsausdrucks. Die **führen-während** -Anweisung kann auch beendet, wenn eine [Break](../cpp/break-statement-cpp.md), [Goto](../cpp/goto-statement-cpp.md), oder [zurückgeben](../cpp/return-statement-cpp.md) -Anweisung innerhalb des Anweisungstexts ausgeführt wird.  
  
 Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen. Die Ausführung erfolgt folgendermaßen:  
  
1.  Der Anweisungstext wird ausgeführt.  
  
2.  Danach wird *expression*, der Ausdruck, ausgewertet. Wenn *Ausdruck* ist "false", die **führen-während** -Anweisung beendet und das Steuerelement an die nächste Anweisung im Programm weitergegeben. Wenn *expression* „true“ (ungleich 0 [null]) ist, wird der Prozess wiederholt, beginnend mit Schritt 1.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die **sind – während** Anweisung:  
  
```cpp 
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Iterationsanweisungen](../cpp/iteration-statements-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [while-Anweisung (C++)](../cpp/while-statement-cpp.md)   
 [for-Anweisung (C++)](../cpp/for-statement-cpp.md)   
 [Bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md)