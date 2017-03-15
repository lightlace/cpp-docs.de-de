---
title: "Ccos, Ccosf, ccosl | Microsoft Docs"
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
  - "ccos"
  - "ccosf"
  - "ccosl"
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
  - "ccos"
  - "ccosf"
  - "ccosl"
  - "complex/ccos"
  - "complex/ccosf"
  - "complex/ccosl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ccos-Funktion"
  - "Ccosf-Funktion"
  - "Ccosl-Funktion"
ms.assetid: 4ab936ac-ff85-49ac-9418-2b69cf5d4696
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ccos, Ccosf, ccosl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Kosinus einer komplexen Zahl ab.  
  
## Syntax  
  
```  
_Dcomplex ccos(   
   _Dcomplex z   
);  
_Fcomplex ccos(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex ccos(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex ccosf(   
   _Fcomplex z   
);  
_Lcomplex ccosl(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl, die den Winkel im Bogenmaß darstellt.  
  
## Rückgabewert  
 Der Kosinus von `z`, im Bogenmaß.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `ccos` aufrufen, die `_Fcomplex`\- und `_Lcomplex`\-Werte verwenden und zurückgeben. In einem C\-Programm `ccos` immer Double und gibt ein `_Dcomplex` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`ccos`, `ccosf`, `ccosl`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Catanh, Catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [Ctanh, Ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [Catan, Catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [Csinh, Csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [Casinh, Casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [Ccosh, Ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [Cacosh, Cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [Cacos, Cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [Ctan, Ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [Csin, Csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [Casin, Casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [Csqrt, Csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)