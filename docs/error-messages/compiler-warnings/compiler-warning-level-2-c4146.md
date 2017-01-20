---
title: "Compilerwarnung (Stufe 2) C4146"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4146"
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einem vorzeichenlosen Typ wurde ein unärer Operator Minus zugewiesen. Das Ergebnis ist weiterhin vorzeichenlos.  
  
 Vorzeichenlose Typen können ausschließlich nicht negative Werte enthalten, sodass eine auf einen vorzeichenlosen Typ angewendete Negation \(unärer Operator Minus\) in der Regel keinen Sinn ergibt.  Sowohl der Operand als auch das Ergebnis sind nicht negativ.  
  
 In der Praxis tritt diese Situation ein, wenn der Programmierer versucht, den minimalen Ganzzahlwert, d. h. \-2147483648, auszudrücken.  Dieser Wert kann nicht mit "\-2147483648" dargestellt werden, da der Ausdruck in zwei Schritten verarbeitet wird:  
  
1.  Die Zahl 2147483648 wird ausgewertet.  Da größer als der maximale Ganzzahlwert 2147483647, hat 2147483648 nicht den Typ [int](../../c-language/integer-types.md), sondern `unsigned int`.  
  
2.  Der unäre Operator Minus wird auf den Wert angewendet. Dies führt zu einem vorzeichenlosen Ergebnis, das zufällig auch den Wert 2147483648 hat.  
  
 Der vorzeichenlose Typ des Ergebnisses kann zu unerwartetem Verhalten führen.  Falls das Ergebnis in einem Vergleich verwendet wird, sollte dieser, beispielsweise wenn der andere Operand ein `int`\-Typ ist, ohne Vorzeichen durchgeführt werden.  Dies ist der Grund dafür, dass das unten aufgeführte Beispielprogramm lediglich eine Zeile ausgibt.  
  
 Die erwartete zweite Zeile `1 is greater than the most negative int` wird nicht ausgegeben, da `((unsigned int)1) > 2147483648`  "false" ist.  
  
 Um C4146 zu vermeiden, verwenden Sie INT\_MIN aus "limits.h" mit dem Typ **signed int**.  
  
## Beispiel  
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