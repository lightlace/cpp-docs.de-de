---
title: "__movsq | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__movsq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__movsq intrinsic"
  - "rep movsq-Anweisung"
  - "movsq-Anweisung"
ms.assetid: be116a6e-2176-4ca4-93b1-9ccf3e7e7835
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __movsq
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert eine wiederholte Anweisung der Verschiebungs\-Zeichenfolge \(`rep movsq`\).  
  
## Syntax  
  
```  
void __movsq(   
   unsigned char* Dest,   
   unsigned char* Source,   
   size_t Count   
);  
```  
  
#### Parameter  
 \[out\] `Dest`  
 Das Ziel des Vorgangs.  
  
 \[in\] `Source`  
 Die Quelle des Vorgangs.  
  
 \[in\] `Count`  
 Die Anzahl der zu kopierenden Quadwords.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__movsq`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das Ergebnis ist, dass die ersten `Count` Quadwords, die durch `Source` dargestellt werden, auf die `Dest` Zeichenfolge kopiert werden.  
  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Beispiel  
  
```  
// movsq.cpp  
// processor: x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsq)  
  
int main()  
{  
    unsigned __int64 a1[10];  
    unsigned __int64 a2[10] = {950, 850, 750, 650, 550, 450, 350, 250,  
                               150, 50};  
    __movsq(a1, a2, 10);  
  
    for (int i = 0; i < 10; i++)  
       printf_s("%d ", a1[i]);  
    printf_s("\n");  
}  
```  
  
  **950 850 750 650 550 450 350 250 150 50**    
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)