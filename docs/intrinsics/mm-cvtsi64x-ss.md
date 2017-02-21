---
title: "_mm_cvtsi64x_ss | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_cvtsi64x_ss"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cvtsi2ss-Anweisung"
  - "_mm_cvtsi64x_ss (systemintern)"
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_cvtsi64x_ss
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] erweiterte Version der Bekehrt64\-bit\-ganzzahl zur skalaren Anweisung des Gleitkommazahl mit einfacher Genauigkeit \(`cvtsi2ss`\).  
  
## Syntax  
  
```  
__m128 _mm_cvtsi64x_ss(   
   __m128 a,   
   __int64 b   
);  
```  
  
#### Parameter  
 \[in\] `a`  
 Eine `__m128` Struktur, die vier Gleitkommazahlen mit einfacher Genauigkeit enthält.  
  
 \[in\] `b`  
 Eine in einen Gleitkommawert zu konvertierende 64\-Bit\-Ganzzahl.  
  
## Rückgabewert  
 Eine `__m128` Struktur, deren erster Gleitkommawert das Ergebnis der Konvertierung darstellt.  Die anderen drei Werte werden von `a`unverändert kopiert.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_mm_cvtsi64x_ss`|x64|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Die `__m128` Struktur stellt ein XMM\-Register dar, sodass können systeminterne den Wert in ein vom `b` XMM\-Register zu verschiebenden Systemspeicher.  
  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Beispiel  
  
```  
// _mm_cvtsi64x_ss.cpp  
// processor: x64  
  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtsi64x_ss)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    a.m128_f32[0] = 0;  
    a.m128_f32[1] = 0;  
    a.m128_f32[2] = 0;  
    a.m128_f32[3] = 0;  
    a = _mm_cvtsi64x_ss(a, b);  
  
    printf_s( "%lf %lf %lf %lf\n",  
              a.m128_f32[0], a.m128_f32[1],   
              a.m128_f32[2], a.m128_f32[3] );  
}  
```  
  
  **54.000000 0.000000 0.000000 0.000000**   
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [\_\_m128](../cpp/m128.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)