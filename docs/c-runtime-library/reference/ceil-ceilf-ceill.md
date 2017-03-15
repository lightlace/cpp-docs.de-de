---
title: "ceil, ceilf, ceill | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ceilf"
  - "ceil"
  - "ceill"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "ceil"
  - "ceilf"
  - "ceill"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Berechnen der Werteobergrenze"
  - "ceil-Funktion"
  - "ceilf-Funktion"
  - "ceil-Funktion"
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ceil, ceilf, ceill
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet die nächstliegende nicht größere ganze Zahl eines Werts.  
  
## Syntax  
  
```  
double ceil(   
   double x   
);  
float ceil(  
   float x  
);  // C++ only  
long double ceil(  
   long double x  
);  // C++ only  
float ceilf(  
   float x  
);  
long double ceill(  
   long double x  
);  
```  
  
#### Parameter  
 `x`  
 Gleitkommawert.  
  
## Rückgabewert  
 Die `ceil`\-Funktionen geben einen Gleitkommawert zurück, der die kleinste ganze Zahl darstellt, die größer oder gleich `x` ist.  Es gibt keine Fehlerrückgabe.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± `QNAN`,`IND`|Keine|`_DOMAIN`|  
  
 `ceil` ist eine Implementierung, die SIMD\-Streamingerweiterungen 2 \(SSE2\) verwendet.  Informationen und Einschränkungen zur Verwendung der SSE2\-Implementierung finden Sie unter [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
## Hinweise  
 Da C\+\+ ein Überladen zulässt, können Sie Überladungen von `ceil` aufrufen.  In einem C\-Programm verwendet `ceil` immer double und gibt auch double zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`ceil`, `ceilf`, `ceill`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Betrachten Sie das Beispiel für [floor](../../c-runtime-library/reference/floor-floorf-floorl.md).  
  
## .NET Framework-Entsprechung  
 [System::Math::Ceiling](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)