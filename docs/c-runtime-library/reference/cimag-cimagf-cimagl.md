---
title: "Cimag, Cimagf, cimagl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "cimag"
  - "cimagf"
  - "cimagl"
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
  - "cimagf"
  - "cimagl"
  - "complex/cimag"
  - "complex/cimagf"
  - "complex/cimagl"
  - "cimag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cimag-Funktion"
  - "Cimagf-Funktion"
  - "Cimagl-Funktion"
ms.assetid: 0d8836f5-d61d-44cd-8731-6f75cb776def
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Cimag, Cimagf, cimagl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die imaginäre Teil einer komplexen Zahl ab.  
  
## Syntax  
  
```  
double cimag(   
   _Dcomplex z   
);  
float cimag(   
   _Fcomplex z   
);  // C++  
long double cimag(   
  _Lcomplex z   
);  // C++  
float cimagf(   
   _Fcomplex z   
);  
long double cimagl(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl.  
  
## Rückgabewert  
 Der imaginäre Teil von `z`.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `cimag` nehmen `_Fcomplex` oder `_Lcomplex` Werte und Rückgabetypen `float` oder `long double` Werte. In einem C\-Programm `cimag` immer einen `_Dcomplex` Wert und gibt einen `double` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`cimag`, `cimagf`, `cimagl`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Norm, Normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [Creal, Crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [Cproj, Cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [Conj, Conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [Carg, Cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [CAB\-Dateien, Cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)