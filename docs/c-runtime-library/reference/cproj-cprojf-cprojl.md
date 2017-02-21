---
title: "Cproj, Cprojf, cprojl | Microsoft Docs"
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
  - "cproj"
  - "cprojf"
  - "cprojl"
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
  - "cproj"
  - "cprojf"
  - "cprojl"
  - "complex/cproj"
  - "complex/cprojf"
  - "complex/cprojl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cproj-Funktion"
  - "Cprojf-Funktion"
  - "Cprojl-Funktion"
ms.assetid: 32b49623-13bf-4cae-802e-7912d75030fe
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Cproj, Cprojf, cprojl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Projektion einer komplexen Zahl auf die Kugel Reimann ab.  
  
## Syntax  
  
```  
_Dcomplex cproj(   
   _Dcomplex z   
);  
_Fcomplex cproj(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex cproj(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex cprojf(   
   _Fcomplex z   
);  
_Lcomplex cprojl(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl.  
  
## Rückgabewert  
 Die Projektion `z` auf die Reimann Kugel.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `cproj` aufrufen, die `_Fcomplex`\- und `_Lcomplex`\-Werte verwenden und zurückgeben. In einem C\-Programm `cproj` immer Double und gibt ein `_Dcomplex` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`cproj`, `cprojf`, `cprojl`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Norm, Normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [Creal, Crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [Conj, Conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [Cimag, Cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [Carg, Cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [CAB\-Dateien, Cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)