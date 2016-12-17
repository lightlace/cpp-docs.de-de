---
title: "Norm, Normf, norml"
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
  - "norm"
  - "normf"
  - "norml"
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
  - "norm"
  - "normf"
  - "norml"
  - "complex/norm"
  - "complex/normf"
  - "complex/norml"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "norm-Funktion"
  - "Normf-Funktion"
  - "Norml-Funktion"
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Norm, Normf, norml
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die quadratischen Größe einer komplexen Zahl ab.  
  
## Syntax  
  
```  
double norm(   
   _Dcomplex z   
);  
float norm(   
   _Fcomplex z   
);  // C++ only  
long double norm(   
  _Lcomplex z   
);  // C++ only  
float normf(   
   _Fcomplex z   
);  
long double norml(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl.  
  
## Rückgabewert  
 Das Quadrat Ausmaß des `z`.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `norm` nehmen `_Fcomplex` oder `_Lcomplex` Werte und Rückgabetypen `float` oder `long double` Werte. In einem C\-Programm `norm` immer einen `_Dcomplex` Wert und gibt einen `double` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`norm`, `normf`, `norml`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Creal, Crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [Cproj, Cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [Conj, Conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [Cimag, Cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [Carg, Cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [CAB\-Dateien, Cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)