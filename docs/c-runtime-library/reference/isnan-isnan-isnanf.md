---
title: "IsNaN, _isnan, _isnanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isnan"
  - "_isnanf"
  - "isnan"
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
  - "_isnan"
  - "isnan"
  - "math/isnan"
  - "math/_isnan"
  - "math/_isnanf"
  - "_isnanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NAN ("Not a Number", keine Zahl)"
  - "_isnan-Funktion"
  - "IEEE-Gleitkommadarstellung"
  - "Not a Number, keine Zahl (NANs)"
  - "isnan-Funktion"
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# IsNaN, _isnan, _isnanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Testet, ob ein Gleitkommawert ist keine Zahl \(NAN\).  
  
## Syntax  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### Parameter  
 *w*  
 Der zu testende Gleitkommawert.  
  
## Rückgabewert  
 In C ist die `isnan` Makro und die `_isnan` und `_isnanf` Funktionen einen Wert ungleich NULL zurück, wenn das Argument `x` ist ein NAN; andernfalls geben sie 0 zurück.  
  
 In C\+\+ wird die `isnan` Vorlage Funktionen zurückgeben `true` Wenn das Argument `x` ist ein NAN; andernfalls geben sie zurück `false`.  
  
## Hinweise  
 C `isnan` Makro und die `_isnan` und `_isnanf` Gleitkommawert zu testen *x*, einen Wert ungleich NULL zurückgeben, wenn *x* ist keine Zahl \(NAN\)\-Wert. Ein NaN\-Wert wird generiert, wenn das Ergebnis einer Gleitkommaoperation in IEEE\-754 Gleitkommaformat für den angegebenen Typ dargestellt werden kann. Weitere Informationen dazu, wie ein NaN\-Wert für die Ausgabe dargestellt wird, finden Sie unter [Printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 Wenn als C\+\+ kompiliert die `isnan` Makro ist nicht definiert, und ein `isnan` Vorlagenfunktion stattdessen definiert ist. Sie gibt einen Wert vom Typ `bool` anstelle einer Zahl.  
  
 Die `_isnan` und `_isnanf` Funktionen sind Microsoft\-spezifisch. Die `_isnanf` Funktion ist nur verfügbar, wenn für X64 kompiliert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header \(C\)|Erforderlicher Header \(C\+\+\)|  
|-------------|---------------------------------|-------------------------------------|  
|`isnan`, `_isnanf`|\<math.h\>|\<math.h\> oder \<cmath\>|  
|`_isnan`|\<float.h\>|\< float.h \> oder \< Cfloat \>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [\_finite, \_finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [\_fpclass \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)