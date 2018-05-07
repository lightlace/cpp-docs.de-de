---
title: Compilerwarnung (Stufe 2) C4146 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4146
dev_langs:
- C++
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40a94d2aed0b455fda646214f4488c53045b7f6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4146"></a>Compilerwarnung (Stufe 2) C4146
Typ ohne Vorzeichen, wurde ein unäres minus-Operator angewendet.  
  
 Vorzeichenlose Typen können nur nicht Negative Werte enthalten, sodass unäres minus (Negation) keine in der Regel sinnvoll, wenn auf einen vorzeichenlosen Typ angewendet. Der Operand und das Ergebnis sind nicht negativ.  
  
 Dies tritt praktisch, wenn der Programmierer versucht, den minimalen Ganzzahlwert express, der-2147483648 ist. Dieser Wert kann nicht als-2147483648 geschrieben werden, da der Ausdruck in zwei Stufen verarbeitet wird:  
  
1.  Die Zahl 2147483648 wird ausgewertet. Da sie größer als der maximale ganzzahlige Wert von 2147483647 ist, ist der Typ des 2147483648 nicht [Int](../../c-language/integer-types.md), aber `unsigned int`.  
  
2.  Unäres minus wird auf den Wert auch dann der Fall sein 2147483648 angewendet.  
  
 Der unsignierte Typ des Ergebnisses kann zu unerwartetem Verhalten führen. Wenn das Ergebnis wird in einem Vergleich verwendet, und klicken Sie dann ein Vergleich ohne Vorzeichen werden, z. B., verwendet kann Wenn der andere Operand ist ein `int`. Hier wird erläutert, warum das folgenden Beispielprogramm lediglich eine Zeile ausgibt.  
  
 Die erwartete zweite Zeile `1 is greater than the most negative int`, wird nicht ausgegeben werden, da `((unsigned int)1) > 2147483648` lautet "false".  
  
 Sie können C4146 vermeiden, indem Sie INT_MIN aus limits.h den Typ hat **signiert Int**.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4146 generiert:  
  
```  
// C4146.cpp  
// compile with: /W2  
#include <stdio.h>  
  
void check(int i)   
{  
    if (i > -2147483648)   // C4146  
        printf_s("%d is greater than the most negative int\n", i);  
}  
  
int main()   
{  
    check(-100);  
    check(1);  
}  
```