---
title: "_mm_insert_si64, _mm_inserti_si64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_inserti_si64"
  - "_mm_insert_si64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insertq-Anweisung"
  - "_mm_insert_si64 intrinsic"
  - "_mm_inserti_si64 intrinsic"
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_insert_si64, _mm_inserti_si64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `insertq`\-Anweisung, Bits des zweiten Operanden in den ersten Operanden eingefügt werden soll.  
  
## Syntax  
  
```  
__m128i _mm_insert_si64(  
   __m128i Source1,  
   __m128i Source2  
);  
__m128i _mm_inserti_si64(  
   __m128i Source1,  
   __m128i Source2  
   int Length,  
   int Index  
);  
```  
  
#### Parameter  
 \[in\] `Source1`  
 Ein 128\-Bit\-Feld mit Eingabedaten in seinen unteren 64 Bits, in die das Feld eingefügt wird.  
  
 \[in\]    `Source2`  
 Ein 128\-Bit\-Feld mit den in seine niedrigen Bits Daten einzufügen.  Ein Deskriptor Feld enthält außerdem einen `_mm_insert_si64`in seinen hohen Bits.  
  
 \[in\]    `Length`  
 Eine ganzzahlige Konstante, die die Länge des Felds angibt, das eingefügt werden soll.  
  
 \[in\]    `Index`  
 Eine ganzzahlige Konstante, die den Index des niedrigstwertigen Byte des Felds angibt, in die Daten eingefügt werden.  
  
## Rückgabewert  
 Ein 128\-Bit\-Feld, dessen unteren 64 Bits der ursprüngliche unteren 64 Bits der `Source1` mit dem angegebenen Bitfeld enthalten, durch die ersetzte niedrigen Bits von `Source2`.  Die oberen 64 Bits des Rückgabewerts ist nicht definiert.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_mm_insert_si64`|SSE4a|  
|`_mm_inserti_si64`|SSE4a|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das systeminterne generiert die `insertq`\-Anweisung, Bits von `Source2` in `Source1`eingefügt werden soll.  Es gibt zwei Versionen des systeminternen: `_mm_inserti_si64`, ist die unmittelbaren Freigabe, und `_mm_insert_si64` ist das nicht\-unmittelbare.  Jede Version extrahiert ein Bitfeld einer angegebenen Länge von Source2 und fügt es in Source1 ein.  Die niedrigstwertigen Bits enthalten die extrahierten Source2 von Bytes.  Das Feld Source1, in das diese Bits eingefügt werden, wird durch die Länge und den Index des niedrigstwertigen Byte definiert.  Die Werte werden der Index und eine Länge von 64 MOD, so sind \-1 und 127 als 63 interpretiert.  Wenn die Summe aus \(reduziert\) \(reduzierte\) des Felds Länge des Index und ist größer als 64 Bit, sind die Ergebnisse nicht definiert.  Ein Feld für den Wert Null Länge des wird als 64 interpretiert.  Wenn der Feld längen\- und \- Bit Zeilenindex der Nullen sind, werden in `Source2` von 63:0 Bit `Source1`eingefügt.  Wenn die Länge des Felds null ist, aber der Bit Index ungleich 0 \(null\) ist, sind die Ergebnisse nicht definiert.  
  
 In einem Aufruf von \_mm\_insert\_si64, wird die Länge des Felds im Source2 von 77:72 Bit im Index und Bit im 69:64 Uhr enthalten.  
  
 Wenn Sie `_mm_inserti_si64`mit Argumenten aufgerufen werden, die der Compiler nicht ermitteln kann, um ganzzahlige Konstanten sind, generiert der Compiler Code, um diese Werte zu packen und XMM\-Register in ein `_mm_insert_si64`aufzurufen.  
  
 Um Hardwareunterstützung für die `insertq`\-Anweisung zu bestimmen `__cpuid` direkt aufrufen und `InfoType=0x80000001` mit Prüfbit 6 von `CPUInfo[2] (ECX)`.  Das Bit beträgt 1, wenn die Anweisung unterstützt wird, andernfalls 0.  Wenn Sie diesen Code ausführen, der Hardware, das auf die ist, die nicht direkt `insertq`\-Anweisung unterstützt, die Ergebnisse sind unvorhersehbar.  
  
## Beispiel  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source1, source2, source3, result1, result2, result3;  
  
int  
main()  
{  
  
    __int64 mask;  
  
    source1.ui64[0] = 0xffffffffffffffffll;  
    source2.ui64[0] = 0xfedcba9876543210ll;  
    source2.ui64[1] = 0xc10;  
    source3.ui64[0] = source2.ui64[0];  
  
    result1.m = _mm_insert_si64 (source1.m, source2.m);  
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);  
    mask = 0xffff << 12;  
    mask = ~mask;  
    result3.ui64[0] = (source1.ui64[0] & mask) |  
                      ((source2.ui64[0] & 0xffff) << 12);  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
  
}  
```  
  
  **result1 \= 0xfffffffff3210fff**  
**result2 \= 0xfffffffff3210fff**  
**result3 \= 0xfffffffff3210fff**   
## Microsoft ENDES bestimmten  
 Copyright 2007 bis Advanced Micro Devices, Inc.  Alle Rechte vorbehalten.  Reproduziert mit zulässigen Advanced Micro Devices, Inc.  
  
## Siehe auch  
 [\_mm\_extract\_si64, \_mm\_extracti\_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)