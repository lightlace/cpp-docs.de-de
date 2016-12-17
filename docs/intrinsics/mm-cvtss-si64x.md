---
title: "_mm_cvtss_si64x"
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
  - "_mm_cvtss_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cvtss2si intrinsic"
  - "_mm_cvtss_si64x intrinsic"
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# _mm_cvtss_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] erweiterte Version der Bekehrt\-skalaren einfache Genauigkeits\-Gleitkommazahl der Anweisung der 64\-Bit\-Ganzzahl \(`cvtss2si`\).  
  
## Syntax  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### Parameter  
 \[in\] `value`  
 Eine `__m128` Struktur mit Gleitkommazahlen enthält.  
  
## Rückgabewert  
 Eine 64\-Bit\-Ganzzahl, das Ergebnis der Konvertierung des ersten Gleitkommazahl in eine ganze Zahl.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das erste Element des Werts wird Struktur in eine ganze Zahl konvertiert und zurückgegeben.  Die abgerundeten Steuerbite in MXCSR werden verwendet, um das Rundungsverhalten zu bestimmen.  Der standardmäßige gerundete Modus befindet und sich um zur gerade Zahl gerundet, wenn der dezimale Teil 0.5 ist.  Da die `__m128` Struktur ein XMM\-Register darstellt, nimmt diese systeminterne einen Wert aus dem XMM\-Register und schreibt ihn auf den Systemspeicher.  
  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Beispiel  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
  **101**   
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [\_\_m128d](../cpp/m128d.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)