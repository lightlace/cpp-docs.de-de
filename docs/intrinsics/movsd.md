---
title: "__movsd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__movsd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep movsd-Anweisung"
  - "__movsd intrinsic"
  - "movsd-Anweisung"
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __movsd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert eine Anweisung der Verschiebungs\-Zeichenfolge \(`rep movsd`\).  
  
## Syntax  
  
```  
void __movsd(   
   unsigned long* Dest,   
   unsigned long* Source,   
   size_t Count   
);  
```  
  
#### Parameter  
 \[out\] `Dest`  
 Das Ziel des Vorgangs.  
  
 \[in\] `Source`  
 Die Quelle des Vorgangs.  
  
 \[in\] `Count`  
 Die Anzahl der zu kopierenden Doppelworten.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__movsd`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das Ergebnis ist, dass die ersten `Count` Doppelworte, die durch `Source` dargestellt werden, auf die `Dest` Zeichenfolge kopiert werden.  
  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Beispiel  
  
```  
// movsd.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsd)  
  
int main()  
{  
    unsigned long a1[10];  
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,  
                            250, 150, 50};  
    __movsd(a1, a2, 10);  
  
    for (int i = 0; i < 10; i++)  
        printf_s("%d ", a1[i]);  
    printf_s("\n");  
}  
```  
  
  **950 850 750 650 550 450 350 250 150 50**    
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)