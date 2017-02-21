---
title: "_mm_stream_ss | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_stream_ss"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "movntss-Anweisung"
  - "_mm_stream_ss intrinsic"
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mm_stream_ss
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Schreibt 32\-Bit\-Bezugspunkte an einer bestimmten Speicheradresse, ohne den Cache zu verunreinigen.  
  
## Syntax  
  
```  
void _mm_stream_ss(  
   float * Dest,  
   __m128 Source  
);  
```  
  
#### Parameter  
 \[out\] `Dest`  
 Ein Zeiger auf den Speicherort, an dem die Quelldaten geschrieben werden.  
  
 \[in\] `Source`  
 Eine 128\-Bit\-Zahl, die den in der Bits enthält, die geschrieben werden sollen `float`\-Wert, der unteren 32.  
  
## Rückgabewert  
 Keine.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_mm_stream_ss`|SSE4a|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das systeminterne generiert die `movntss`Anweisung.  Um Hardwareunterstützung für diese Anweisung zu bestimmen, `__cpuid` direkt mit `InfoType=0x80000001`Rufen Sieund Prüfbit 6 von `CPUInfo[2] (ECX)`.  Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0.  
  
 Wenn Sie Code ausführen, der verwendet `_mm_stream_ss` auf Hardware systemintern ist, die nicht den `movntss`\-Anweisung unterstützt, die Ergebnisse sind unvorhersehbar.  
  
## Beispiel  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128 vals;  
    float f[4];  
  
    f[0] = -1.;  
    f[1] = -2.;  
    f[2] = -3.;  
    f[3] = -4.;  
    vals.m128_f32[0] = 0.;  
    vals.m128_f32[1] = 1.;  
    vals.m128_f32[2] = 2.;  
    vals.m128_f32[3] = 3.;  
    _mm_stream_ss(&f[3], vals);  
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;  
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;  
}  
  
```  
  
  **f \[0\] \= \-1, f \[1\] \= \-2**  
**f \[2\] \= \-3, f \[3\] \= 3**   
## Microsoft ENDES bestimmten  
 Copyright 2007 bis Advanced Micro Devices, Inc.  Alle Rechte vorbehalten.  Reproduziert mit zulässigen Advanced Micro Devices, Inc.  
  
## Siehe auch  
 [\_mm\_stream\_sd](../intrinsics/mm-stream-sd.md)   
 [\_mm\_stream\_ps](assetId:///f7af2f19-c0d4-43c6-b5f6-a658d2b1d869)   
 [\_mm\_store\_ss](assetId:///dfeeea35-8faf-4f54-8a9e-6723e226fb08)   
 [\_mm\_sfence](assetId:///b6c0d18e-3628-4318-826b-45f66782e870)   
 [Streaming SIMD Extensions that Support the Cache](assetId:///8f03493a-d5f5-4457-892e-0b6540494872)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)