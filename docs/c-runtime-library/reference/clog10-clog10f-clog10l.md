---
title: "clog10, clog10f, clog10l | Microsoft Docs"
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
  - "clog10"
  - "clog10f"
  - "clog10l"
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
  - "clog10"
  - "clog10f"
  - "clog10l"
  - "complex/clog10"
  - "complex/clog10f"
  - "complex/clog10l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clog10-Funktion"
  - "clog10f-Funktion"
  - "clog10l-Funktion"
ms.assetid: 2ddae00d-ef93-4441-add3-f4d58358401b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# clog10, clog10f, clog10l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Logarithmus zur Basis 10 einer komplexen Zahl ab.  
  
## Syntax  
  
```  
_Dcomplex clog10(   
   _Dcomplex z   
);  
_Fcomplex clog10(   
  _Fcomplex z   
);  // C++ only  
_Lcomplex clog10(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clog10f(   
   _Fcomplex z   
);  
_Lcomplex clog10l(   
   _Lcomplex z   
);  
```  
  
#### Parameter  
 `z`  
 Die Basis des Logarithmus.  
  
## Rückgabewert  
 Die möglichen Rückgabewerte sind:  
  
|Z\-parameter|Rückgabewert|  
|------------------|------------------|  
|Positiv|Der Logarithmus zur Basis 10 von z|  
|Zero|\- ∞|  
|Negativ|NaN|  
|NaN|NaN|  
|\+ ∞|\+ ∞|  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `clog10` aufrufen, die `_Fcomplex`\- und `_Lcomplex`\-Werte verwenden und zurückgeben. In einem C\-Programm `clog10` immer Double und gibt ein `_Dcomplex` Wert.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`clog10`, `clog10f`, `clogl`|\<complex.h\>|\< Ccomplex \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp, cexpf, cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [Cpow, Cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [CLOG, Clogf, clogl](../../c-runtime-library/reference/clog-clogf-clogl.md)