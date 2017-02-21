---
title: "_finite, _finitef | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_finite"
  - "_finitef"
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
  - "finite"
  - "_finite"
  - "_finitef"
  - "math/_finite"
  - "math/_finitef"
  - "float/_finite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "finite-Funktion"
  - "_finite-Funktion"
  - "_finitef function"
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _finite, _finitef
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein Gleitkommawert endlich ist.  
  
## Syntax  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### Parameter  
 `x`  
 Der zu testende Gleitkommawert.  
  
## Rückgabewert  
 `_finite` und `_finitef` geben einen Wert ungleich NULL zurück, wenn das Argument *x* endlich ist, d. h., wenn –INF \< `x` \< \+INF. 0 \(null\), wenn das Argument unendlich oder ein NaN\-Wert ist.  
  
## Hinweise  
 Die `_finite` und `_finitef` Funktionen sind Microsoft\-spezifisch. Die `_finitef` \-Funktion ist nur verfügbar, wenn für X86, ARM oder ARM64 Plattformen kompiliert.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header \(C\)|Erforderlicher Header \(C\+\+\)|  
|--------------|---------------------------------|-------------------------------------|  
|`_finite`|\<float.h\> oder \<math.h\>|\<float.h\>, \<math.h\>, \<cfloat\> oder \<cmath\>|  
|`_finitef`|\<math.h\>|\<math.h\> oder \<cmath\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 [System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [IsNaN, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [\_fpclass \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)