---
title: "Compilerwarnung (Stufe 3) C4738 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4738"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4738"
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 3) C4738
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im Arbeitsspeicher wird ein 32\-Bit\-Gleitkommaergebnis gespeichert. Es liegt möglicherweise ein Leistungsverlust vor.  
  
 C4738 warnt davor, dass das Ergebnis einer Zuweisung oder Umwandlung, eines weitergegebenen Arguments oder einer anderen Operation unter Umständen gerundet werden muss, oder dass die Operation über keine Register mehr verfügt und dadurch gezwungen wird, Arbeitspeicher zu belegen \(Registerüberlauf\).  Dies kann zu einem Leistungsverlust führen.  
  
 Um diese Warnung und das Runden von Operationen zu vermeiden, kompilieren Sie mit [\/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md), oder verwenden Sie `double` anstelle von `float`.  
  
 Um diese Warnung und einen Registerüberlauf zu vermeiden, ändern Sie die Reihenfolge der Berechnungen und die Verwendung von Inlining.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4738 generiert:  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```