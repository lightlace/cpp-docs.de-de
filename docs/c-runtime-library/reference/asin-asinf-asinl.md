---
title: "asin, asinf, asinl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "asinf"
  - "asinl"
  - "asin"
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
  - "asin"
  - "asinl"
  - "asinf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arkussinus"
  - "asin-Funktion"
  - "asinf-Funktion"
  - "asinl-Funktion"
  - "Trigonometrische Funktionen"
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# asin, asinf, asinl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den Arkussinus.  
  
## Syntax  
  
```  
double asin(   
   double x   
);  
float asin(  
   float x  
);  // C++ only  
long double asin(  
   long double x  
);  // C++ only  
float asinf (   
   float x   
);  
long double asinl(  
   long double x  
);  
```  
  
#### Parameter  
 `x`  
 Wert, dessen Arkussinus berechnet werden soll.  
  
## Rückgabewert  
 Die `asin`\-Funktion gibt den Arkussinus \(die umgekehrte Sinusfunktion\) von `x` im Bereich \-π\/2 bis π\/2 Bogenmaße zurück.  
  
 Wenn `x` kleiner als – 1 oder größer als 1 ist, gibt `asin` standardmäßig einen unbestimmten Wert zurück.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± `QNAN`,`IND`|Keine|`_DOMAIN`|  
|&#124;x&#124;\>1|`INVALID`|`_DOMAIN`|  
  
## Hinweise  
 Da C\+\+ Überladungen zulässt, können Sie Überladungen von `asin` mit den Werten `float` und `long double` aufrufen.  In einem C\-Programm verwendet `asin` immer double und gibt auch double zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`asin`, `asinf`, `asinl`|\<math.h\>|  
  
## Beispiel  
 Weitere Informationen finden Sie unter [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md).  
  
## .NET Framework-Entsprechung  
 [System::Math::Asin](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)