---
title: "Ccosh, Ccoshf, ccoshl"
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
  - "ccosh"
  - "ccoshf"
  - "ccoshl"
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
  - "ccosh"
  - "ccoshf"
  - "ccoshl"
  - "complex/ccosh"
  - "complex/ccoshf"
  - "complex/ccoshl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "Ccosh-Funktion"
  - "Ccoshf-Funktion"
  - "Ccoshl-Funktion"
ms.assetid: 79667449-4edf-4948-bf6b-720adf2b3f3b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Ccosh, Ccoshf, ccoshl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den hyperbolischen Kosinus einer komplexen Zahl ab.  
  
## Syntax  
  
```  
_Dcomplex ccosh(   
   _Dcomplex z   
);  
_Fcomplex ccosh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex ccosh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex ccoshf(   
   _Fcomplex z   
);  
_Lcomplex ccoshl(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl, die den Winkel im Bogenmaß darstellt.  
  
## Rückgabewert  
 Der Hyperbelkosinus von `z`, im Bogenmaß.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `ccosh` aufrufen, die `_Fcomplex`\- und `_Lcomplex`\-Werte verwenden und zurückgeben. In einem C\-Programm `ccosh` immer Double und gibt ein `_Dcomplex` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`ccosh`, `ccoshf`, `ccoshl`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Catanh, Catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [Ctanh, Ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [Catan, Catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [Csinh, Csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [Casinh, Casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [Cacosh, Cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [Cacos, Cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [Ctan, Ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [Csin, Csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [Casin, Casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [Ccos, Ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [Csqrt, Csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)