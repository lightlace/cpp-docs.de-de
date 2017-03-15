---
title: "__stosb | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__stosb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep stosb-Anweisung"
  - "__stosb (systemintern)"
  - "stosb-Anweisung"
ms.assetid: 634589ed-2da3-439b-a381-a214d89bf10c
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# __stosb
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert eine Speicherung von Zeichenfolgen Statement \(`rep stosb`\).  
  
## Syntax  
  
```  
void __stosb(   
   unsigned char* Dest,   
   unsigned char Data,   
   size_t Count   
);  
```  
  
#### Parameter  
 \[out\] `Dest`  
 Das Ziel des Vorgangs.  
  
 \[in\] `Data`  
 Die zu speichernden Daten.  
  
 \[in\] `Count`  
 Die Länge des Blocks zu schreibenden Bytes.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__stosb`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das Ergebnis ist, dass das Zeichen `Data` in einen Block von Bytes in der `Count``Dest` Zeichenfolge geschrieben wird.  
  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Beispiel  
  
```  
// stosb.c  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosb)  
  
int main()  
{  
    unsigned char c = 0x40; /* '@' character */  
    unsigned char s[] = "*********************************";  
  
    printf_s("%s\n", s);  
    __stosb((unsigned char*)s+1, c, 6);  
    printf_s("%s\n", s);  
  
}  
```  
  
  **\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***  
**\*@@@@@@\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***   
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)