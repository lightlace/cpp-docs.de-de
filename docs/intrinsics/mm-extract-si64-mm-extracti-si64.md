---
title: "_mm_extract_si64, _mm_extracti_si64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_extracti_si64"
  - "_mm_extract_si64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extrq-Anweisung"
  - "_mm_extracti_si64 intrinsic"
  - "_mm_extract_si64 intrinsic"
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mm_extract_si64, _mm_extracti_si64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `extrq`\-Anweisung angegebene Bits von den unteren 64 Bits des ersten Arguments zu extrahieren.  
  
## Syntax  
  
```  
__m128i _mm_extract_si64(  
   __m128i Source,  
   __m128i Descriptor  
);  
__m128i _mm_extracti_si64(  
   __m128i Source,  
   int Length,  
   int Index  
);  
```  
  
#### Parameter  
 \[in\] `Source`  
 Ein 128\-Bit\-Feld mit Eingabedaten in seinen unteren 64 Bits.  
  
 \[in\]    `Descriptor`  
 Ein 128\-Bit\-Feld, das das Bitfeld beschreibt, die extrahiert werden soll.  
  
 \[in\]    `Length`  
 Eine ganze Zahl, die die Länge des Felds angibt, die extrahiert werden soll.  
  
 \[in\]    `Index`  
 Eine ganze Zahl, die den Index des zu extrahierenden Felds angibt  
  
## Rückgabewert  
 Ein 128\-Bit\-Feld mit den extrahierten Feld in den niedrigstwertigen Byte.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das systeminterne generiert die `extrq`\-Anweisung, Bits von `Source`zu extrahieren. Es gibt zwei Versionen des systeminternen: `_mm_extracti_si64` ist die direkte Version, und `_mm_extract_si64` ist das nicht\-unmittelbare.  Jede Version von `Source` extrahiert, das ein Bitfeld, durch deren Länge und den Index des niedrigstwertigen Byte definiert ist.  Die Werte werden der Index und eine Länge von 64 MOD, so sind \-1 und 127 als 63 interpretiert.  Wenn die Summe der reduzierten \(\) \(reduzierten\) des Felds Länge des Index und größer als 64 ist, sind die Ergebnisse nicht definiert.  Ein Feld für den Wert Null Länge des wird als 64 interpretiert.  Wenn der Feld längen\- und \- Bit Zeilenindex null sind, werden beide Bits 63:0 von `Source` extrahiert.  Wenn die Länge des Felds null ist, aber der Bit Index ungleich 0 \(null\) ist, sind die Ergebnisse nicht definiert.  
  
 In einem Aufruf von \_mm\_extract\_si64, enthält `Descriptor` den Index im Bit 13:8 und 5:0 Bit in der Länge des Felds zu extrahierenden Daten.  
  
 Wenn Sie aufrufen, generiert `_mm_extracti_si64` mit Argumenten, die der Compiler nicht ermitteln kann, um ganzzahlige Konstanten sind der Compiler Code, um diese Werte in einem XMM\-Register \(`Descriptor`\) zu packen und `_mm_extract_si64`aufzurufen.  
  
 Um Hardwareunterstützung für die `extrq`\-Anweisung zu bestimmen, `__cpuid` direkt aufrufen und `InfoType=0x80000001` mit Prüfbit 6 von `CPUInfo[2] (ECX)`.  Das Bit beträgt 1, wenn die Anweisung unterstützt wird, andernfalls 0.  Wenn Sie Code ausführen, der diese systeminterne Hardware verwendet, die nicht die `extrq`\-Anweisung unterstützt, die Ergebnisse sind unvorhersehbar.  
  
## Beispiel  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source, descriptor, result1, result2, result3;  
  
int  
main()  
{  
    source.ui64[0] =     0xfedcba9876543210ll;  
    descriptor.ui64[0] = 0x0000000000000b1bll;  
  
    result1.m = _mm_extract_si64 (source.m, descriptor.m);  
    result2.m = _mm_extracti_si64(source.m, 27, 11);  
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
}  
```  
  
  **result1 \= 0x30eca86**  
**result2 \= 0x30eca86**  
**result3 \= 0x30eca86**   
## Microsoft ENDES bestimmten  
 Copyright 2007 bis Advanced Micro Devices, Inc.  Alle Rechte vorbehalten.  Reproduziert mit zulässigen Advanced Micro Devices, Inc.  
  
## Siehe auch  
 [\_mm\_insert\_si64, \_mm\_inserti\_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)