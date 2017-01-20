---
title: "Carg, Cargf, cargl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "carg"
  - "cargf"
  - "cargl"
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
  - "carg"
  - "cargf"
  - "cargl"
  - "complex/carg"
  - "complex/cargf"
  - "complex/cargl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "Carg-Funktion"
  - "Cargf-Funktion"
  - "Cargl-Funktion"
ms.assetid: 610d6a93-b929-46ab-a966-b77db0b804be
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Carg, Cargf, cargl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft das Argument für eine komplexe Zahl, mit einer Verzweigung Ausschneiden entlang der negativen real ab.  
  
## Syntax  
  
```  
double carg(   
   _Dcomplex z   
);  
float carg(   
   _Fcomplex z   
);  // C++ only  
long double carg(   
   _Lcomplex z   
);  // C++ only  
float cargf(   
   _Fcomplex z   
);  
long double cargl(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl.  
  
## Rückgabewert  
 Das Argument \(auch bekannt als die Phase\) der `z`. Das Ergebnis ist im Intervall \[−π \+ π\].  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `carg` nehmen `_Fcomplex` oder `_Lcomplex` Werte und Rückgabetypen `float` oder `long double` Werte. In einem C\-Programm `carg` immer einen `_Dcomplex` Wert und gibt einen `double` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`carg`, `cargf`, `cargl`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Norm, Normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [Creal, Crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [Cproj, Cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [Conj, Conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [Cimag, Cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [CAB\-Dateien, Cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)