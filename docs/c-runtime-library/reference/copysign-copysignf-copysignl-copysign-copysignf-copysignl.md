---
title: "copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "copysignf"
  - "copysignl"
  - "_copysignl"
  - "_copysign"
  - "_copysignf"
  - "copysign"
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
  - "_copysignl"
  - "copysign"
  - "copysignf"
  - "_copysign"
  - "copysignl"
  - "_copysignf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_copysign-Funktion"
  - "_copysignf-Funktion"
  - "_copysignl-Funktion"
  - "copysign-Funktion"
  - "copysignf-Funktion"
  - "copysignl-Funktion"
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Wert zurück, der die Größe eines Arguments und das Zeichen eines anderen Arguments aufweist.  
  
## Syntax  
  
```  
double copysign(   
   double x,  
   double y   
);  
float copysign(   
   float x,  
   float y   
); // C++ only  
long double copysign(   
   long double x,  
   long double y   
); // C++ only  
float copysignf(   
   float x,  
   float y   
); // C++ only  
long double copysignl(   
   long double x,  
   long double y   
); // C++ only  
double _copysign(   
   double x,  
   double y   
);  
long double _copysignl(   
   long double x,  
   long double y   
);  
```  
  
#### Parameter  
 `x`  
 Der Gleitkommawert, der als Betrag des Ergebnisses zurückgegeben wird.  
  
 `y`  
 Der Gleitkommawert, der als Zeichen des Ergebnisses zurückgegeben wird.  
  
 [Routinen für die Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)  
  
## Rückgabewert  
 Die `copysign`\-Funktionen geben einen Gleitkommawert zurück, der die Größe von `x` und das Zeichen von `y` kombiniert.  Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `copysign` aufrufen, die `float` oder `long double`\-Werte verwenden und zurückgeben.  In einem C\-Programm verwendet `copysign` immer `double` und gibt diesen Wert zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_copysign`|\<float.h\>|  
|`copysign`, `copysignf`, `copysignl`, `_copysignf` `_copysignl`|\<math.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Fabs, Fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [\_chgsign, \_chgsignf, \_chgsignl](../../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)