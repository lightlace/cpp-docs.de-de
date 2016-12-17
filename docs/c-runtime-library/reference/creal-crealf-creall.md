---
title: "Creal, Crealf, creall"
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
  - "creal"
  - "crealf"
  - "creall"
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
  - "creal"
  - "crealf"
  - "creall"
  - "complex/creal"
  - "complex/crealf"
  - "complex/creall"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "Creal-Funktion"
  - "Crealf-Funktion"
  - "Creall-Funktion"
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Creal, Crealf, creall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Realteil einer komplexen Zahl ab.  
  
## Syntax  
  
```  
double creal(   
   _Dcomplex z   
);  
float creal(   
   _Fcomplex z   
);  // C++ only  
long double creal(   
   _Lcomplex z   
);  // C++ only  
float crealf(   
   _Fcomplex z   
);  
long double creall(   
  _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl.  
  
## Rückgabewert  
 Der reelle Teil von `z`.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `creal` nehmen `_Fcomplex` oder `_Lcomplex` Werte und Rückgabetypen `float` oder `long double` Werte. In einem C\-Programm `creal` immer einen `_Dcomplex` Wert und gibt einen `double` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`creal`, `crealf`, `creall`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Norm, Normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [Cproj, Cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [Conj, Conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [Cimag, Cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [Carg, Cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [CAB\-Dateien, Cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)