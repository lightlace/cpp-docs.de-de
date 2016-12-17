---
title: "Casinh, Casinhf, casinhl"
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
  - "casinh"
  - "casinhl"
  - "casinhf"
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
  - "casinh"
  - "casinhf"
  - "casinhl"
  - "complex/casinh"
  - "complex/casinhf"
  - "complex/casinhl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "Casinh-Funktion"
  - "Casinhf-Funktion"
  - "Casinhl-Funktion"
ms.assetid: bd18340b-21dd-4c86-a14e-e8e15dd97e3b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Casinh, Casinhf, casinhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den umgekehrten hyperbolischen Sinus einer komplexen Zahl, mit der Verzweigung Teilstücke außerhalb des Intervalls \[−i, \+ i\] der imaginäre Achse.  
  
## Syntax  
  
```  
_Dcomplex casinh(   
   _Dcomplex z   
);  
_Fcomplex casinh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex casinh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex casinhf(   
   _Fcomplex z   
);  
_Lcomplex casinhl(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Eine komplexe Zahl, die einen Winkel im Bogenmaß darstellt.  
  
## Rückgabewert  
 Der umgekehrte hyperbolische Sinus des `z`, im Bogenmaß. Das Ergebnis ist der realen Achse, und klicken Sie im Intervall \[−iπ\/2 \+ Iπ\/2\] entlang der imaginären ungebundenen.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `casinh` aufrufen, die `_Fcomplex`\- und `_Lcomplex`\-Werte verwenden und zurückgeben. In einem C\-Programm `casinh` immer Double und gibt ein `_Dcomplex` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`casinh`, `casinhf`, `casinhl`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Catanh, Catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [Ctanh, Ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [Catan, Catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [Csinh, Csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [Ccosh, Ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [Cacosh, Cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [Cacos, Cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [Ctan, Ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [Csin, Csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [Casin, Casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [Ccos, Ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [Csqrt, Csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)