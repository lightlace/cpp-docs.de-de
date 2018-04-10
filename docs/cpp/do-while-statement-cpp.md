---
title: Führen Sie-while-Anweisung (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e03a20ad2b49d5c9337e0c8250e5d7c321ee882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="do-while-statement-c"></a>do-while-Anweisung (C++)
Führt eine *Anweisung* solange wiederholt, bis die angegebene beendigungsbedingung (der *Ausdruck*) wird zu NULL ausgewertet.  
  
## <a name="syntax"></a>Syntax  
  
```  
do  
   statement  
while ( expression ) ;  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Test der Beendigungsbedingung wird nach jeder Ausführung der Schleife durchgeführt. Daher wird eine `do-while`-Schleife einmal oder mehrmals ausgeführt, abhängig vom Wert des Beendigungsausdrucks. Die `do-while` -Anweisung kann auch beendet, wenn eine [Break](../cpp/break-statement-cpp.md), [Goto](../cpp/goto-statement-cpp.md), oder [zurückgeben](../cpp/return-statement-cpp.md) Anweisung innerhalb des Anweisungstexts ausgeführt wird.  
  
 Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen. Die Ausführung erfolgt folgendermaßen:  
  
1.  Der Anweisungstext wird ausgeführt.  
  
2.  Danach wird *expression*, der Ausdruck, ausgewertet. Wenn *expression* „false“ ist, wird die `do-while`-Anweisung beendet und die Steuerung an die nächste Anweisung im Programm weitergegeben. Wenn *expression* „true“ (ungleich 0 [null]) ist, wird der Prozess wiederholt, beginnend mit Schritt 1.  
  
## <a name="example"></a>Beispiel  
 Die `do-while`-Anweisung wird im folgenden Beispiel veranschaulicht:  
  
```  
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