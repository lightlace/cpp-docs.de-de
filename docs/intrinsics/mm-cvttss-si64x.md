---
title: "_mm_cvttss_si64x | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_cvttss_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mm_cvttss_si64x intrinsic"
  - "cvttss2si-Anweisung"
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_cvttss_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Gibt die x64 erweiterte Version des mit einfacher Genauigkeit konvertiert werden soll Abschneiden\-Gleitkommawert mit der Anweisung an`cvttss2si`\(64\-Bit\-Ganzzahl\) ab.  
  
## Syntax  
  
```  
__int64 _mm_cvttss_si64x(   
   __m128 value   
);  
```  
  
#### Parameter  
 \[in\] `value`  
 Eine `__m128` Struktur mit Gleitkommazahlen mit einfacher Genauigkeit enthält.  
  
## Rückgabewert  
 Das Ergebnis der Konvertierung des ersten Gleitkommazahl in eine 64\-Bit\-Ganzzahl.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_mm_cvttss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das systeminterne unterscheidet sich von `_mm_cvtss_si64x` nur dadurch, dass ungenaue Konvertierungen in Richtung Null abgeschnitten werden.  Da die `__m128` Struktur ein XMM\-Register darstellt, richtet die generierte Anweisung Daten aus einem XMM\-Register im Systemspeicher.  
  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Beispiel  
  
```  
// _mm_cvttss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvttss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] = { 101.5, 200.75,  
                                          300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvttss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
  **101**   
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [\_\_m128](../cpp/m128.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)