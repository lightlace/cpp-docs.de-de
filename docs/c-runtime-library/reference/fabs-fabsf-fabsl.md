---
title: "Fabs, Fabsf, fabsl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fabsf"
  - "fabs"
  - "fabsl"
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
  - "fabs"
  - "fabsf"
  - "fabsl"
  - "math\fabs"
  - "math\fabsf"
  - "math\fabsl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Absolute Werte"
  - "fabsf-Funktion"
  - "Berechnen absoluter Werte"
  - "fabs-Funktion"
  - "Fabsl-Funktion"
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Fabs, Fabsf, fabsl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den absoluten Wert des gleitkommaarguments.  
  
## Syntax  
  
```  
double fabs(   
   double x   
);  
float fabs(  
   float x   
); // C++ only  
long double fabs(  
   long double x  
); // C++ only  
float fabsf(   
   float x   
);  
long double fabsl(  
   long double x  
);  
```  
  
#### Parameter  
 `x`  
 Gleitkommawert.  
  
## Rückgabewert  
 Die `fabs` Funktionen geben den absoluten Wert des Arguments zurück `x`. Es gibt keine Fehlerrückgabe.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± QNAN,IND|Keine|\_DOMAIN|  
  
## Hinweise  
 C\+\+ das Überladen, können Sie Überladungen von aufrufen können `fabs` wenn Sie den Header \< Cmath \> einschließen. In einem C\-Programm verwendet `fabs` immer double und gibt auch double zurück.  
  
## Anforderungen  
  
|Funktion|Erforderliche C\-Headerdatei|Erforderlicher C\+\+\-header|  
|--------------|----------------------------------|----------------------------------|  
|`fabs`, `fabsf`, `fabsl`|\<math.h\>|\< Cmath \> oder \< math.h \>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Ein Beispiel hierfür finden Sie unter [abs](../../c-runtime-library/reference/abs-labs-llabs-abs64.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Abs, Labs, Llabs, \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [labs, llabs](../../misc/labs-llabs.md)