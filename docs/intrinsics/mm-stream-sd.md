---
title: "_mm_stream_sd"
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
  - "_mm_stream_sd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mm_stream_sd intrinsic"
  - "movntsd-Anweisung"
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _mm_stream_sd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Schreibt 64\-Bit\-Bezugspunkte an einer bestimmten Speicheradresse, ohne den Cache zu verunreinigen.  
  
## Syntax  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### Parameter  
 \[out\] `Dest`  
 Ein Zeiger auf den Speicherort, an dem die Quelldaten geschrieben werden.  
  
 \[in\] `Source`  
 Ein 128\-Bit\-Wert, der den in seiner Bits geschrieben werden soll `double`\-Wert, der die unteren 64 enthält.  
  
## Rückgabewert  
 Keine.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das systeminterne generiert die `movntsd`Anweisung.  Um Hardwareunterstützung für diese Anweisung zu bestimmen, `__cpuid` direkt aufrufen und `InfoType=0x80000001` mit Prüfbit 6 von `CPUInfo[2] (ECX)`.  Das Bit ist 1, wenn die Hardwareunterstützung diese Anweisung und andernfalls 0.  
  
 Wenn Sie Code ausführen, der verwendet `_mm_stream_sd` auf Hardware systemintern ist, die nicht den `movntsd`\-Anweisung unterstützt, die Ergebnisse sind unvorhersehbar.  
  
## Beispiel  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
  **d \[0\] \= \-1, d \[1\] \= 1**   
## Microsoft ENDES bestimmten  
 Copyright 2007 bis Advanced Micro Devices, Inc.  Alle Rechte vorbehalten.  Reproduziert mit zulässigen Advanced Micro Devices, Inc.  
  
## Siehe auch  
 [\_mm\_stream\_ss](../intrinsics/mm-stream-ss.md)   
 [\_mm\_store\_sd](assetId:///8e672d0d-0a96-45b9-a783-392a2457de42)   
 [\_mm\_sfence](assetId:///b6c0d18e-3628-4318-826b-45f66782e870)   
 [Streaming SIMD Extensions that Support the Cache](assetId:///8f03493a-d5f5-4457-892e-0b6540494872)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)