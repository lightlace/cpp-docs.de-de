---
title: "_mm_stream_si64x | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_stream_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "movnti-Anweisung"
  - "_mm_stream_si64x intrinsic"
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _mm_stream_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die MOVNTI\-Anweisung.  Schreibt die Daten in `Source` an einer bestimmten Speicheradresse, die von `Dest`angegeben wurde, ohne den Cache zu verunreinigen.  
  
## Syntax  
  
```  
void _mm_stream_si64x(   
   __int64 * Dest,   
   __int64 Source   
);  
```  
  
#### Parameter  
 \[out\] `Dest`  
 Ein Zeiger auf den Speicherort, an dem die Quelldaten geschrieben werden soll.  
  
 \[in\] `Source`  
 Die zu schreibenden Daten.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_mm_stream_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Beispiel  
  
```  
// _mm_stream_si64x.c  
// processor: x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_mm_stream_si64x)  
  
int main()  
{  
    __int64 val = 0xFFFFFFFFFFFFI64;  
    __int64 a[10];  
  
    memset(a, 0, sizeof(a));  
    _mm_stream_si64x(a+1, val);  
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);   
}  
```  
  
  **ffffffffffff 0 0 0**   
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Cache Support for Streaming SIMD Extensions 2 Integer Operations](assetId:///a9c9b42f-de9e-4374-aeb6-5f65bfb669b6)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)