---
title: "Csinh, Csinhf, csinhl"
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
  - "csinh"
  - "csinhf"
  - "csinhl"
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
  - "csinh"
  - "csinhf"
  - "csinhl"
  - "complex/csinh"
  - "complex/csinhf"
  - "complex/csinhl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "Csinh-Funktion"
  - "Csinhf-Funktion"
  - "Csinhl-Funktion"
ms.assetid: cc616e55-d14d-4cd3-91f0-fbee03ce5edf
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Csinh, Csinhf, csinhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den hyperbolischen Sinus einer komplexen Zahl ab.  
  
## Syntax  
  
```  
_Dcomplex csinh(   
   _Dcomplex z   
);  
_Fcomplex csinh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex csinh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex csinhf(   
   _Fcomplex z   
);  
_Lcomplex csinhl(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl, die einen Winkel im Bogenmaß darstellt.  
  
## Rückgabewert  
 Der Hyperbelsinus von `z`, im Bogenmaß.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `csinh` aufrufen, die `_Fcomplex`\- und `_Lcomplex`\-Werte verwenden und zurückgeben. In einem C\-Programm `csinh` immer Double und gibt ein `_Dcomplex` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`csinh`, `csinhf`, `csinhl`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Catanh, Catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [Ctanh, Ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [Catan, Catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [Casinh, Casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [Ccosh, Ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [Cacosh, Cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [Cacos, Cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [Ctan, Ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [Csin, Csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [Casin, Casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [Ccos, Ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [Csqrt, Csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)