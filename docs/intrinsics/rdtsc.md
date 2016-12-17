---
title: "__rdtsc"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "__rdtsc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__rdtsc intrinsic"
  - "rdtsc-Anweisung"
  - "Read Time Stamp Counter-Anweisung"
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# __rdtsc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `rdtsc`\-Anweisung, die den Prozessorzeitstempel zurückgibt.  Der Prozessor zeitstempel erfasst die Anzahl der seit der letzten rücksetzung Taktzyklen auf.  
  
## Syntax  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## Rückgabewert  
 Eine 64\-Bit\-Ganzzahl ohne Vorzeichen, die eine Taktanzahl darstellt.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__rdtsc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Routine ist nur als systeminterne Funktion zur Verfügung.  
  
 Die Interpretation des TSC\-Werts in dieser Generation der Hardware unterscheidet sich von dem in früheren Versionen von [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Weitere Informationen finden Sie handbücher Hardware.  
  
## Beispiel  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
  **3363423610155519 Teilstrich**   
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)