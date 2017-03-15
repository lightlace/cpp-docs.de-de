---
title: "Ctanh, Ctanhf, ctanhl | Microsoft Docs"
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
  - "ctanh"
  - "ctahf"
  - "ctahl"
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
  - "ctanh"
  - "ctanhf"
  - "ctanhl"
  - "complex/ctanh"
  - "complex/ctanhf"
  - "complex/ctanhl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ctanh-Funktion"
  - "Ctanhl-Funktion"
  - "Ctanhf-Funktion"
ms.assetid: 807f2cd1-8740-4988-afff-5911c346385b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ctanh, Ctanhf, ctanhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den komplexen hyperbolischen Tangens einer komplexen Zahl.  
  
## Syntax  
  
```  
_Dcomplex ctanh(   
   _Dcomplex z   
);  
_Fcomplex ctanh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex ctanh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex ctanhf(   
   _Fcomplex z   
);  
_Lcomplex ctanhl(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl, die einen Winkel im Bogenmaß darstellt.  
  
## Rückgabewert  
 Der komplexe Hyperbeltangens von `z`.  
  
|Eingabe|SEH\-Ausnahme|`_matherr`\-Ausnahme|  
|-------------|-------------------|--------------------------|  
|± ∞, QNAN, IND|Keine|\_DOMAIN|  
|± ∞ \(tan, Tanf\)|INVALID|\_DOMAIN|  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `ctanh` aufrufen, die `_Fcomplex`\- und `_Lcomplex`\-Werte verwenden und zurückgeben. In einem C\-Programm `ctanh` immer Double und gibt ein `_Dcomplex` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`ctanh`, `ctanhf`, `ctanhl`|\<complex.h\>|\< Ccomplex \>|  
  
 Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Catanh, Catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [Catan, Catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [Csinh, Csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [Casinh, Casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [Ccosh, Ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [Cacosh, Cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [Cacos, Cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [Ctan, Ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [Csin, Csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [Casin, Casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [Ccos, Ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [Csqrt, Csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)