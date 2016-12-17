---
title: "_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_atoldbl"
  - "_atoldbl_l"
  - "_atodbl"
  - "_atoflt"
  - "_atoflt_l"
  - "_atodbl_l"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_atoflt"
  - "_atoflt_l"
  - "atodbl_l"
  - "atoflt_l"
  - "_atoldbl"
  - "_atoldbl_l"
  - "atodbl"
  - "_atodbl_l"
  - "atoldbl"
  - "atoflt"
  - "atoldbl_l"
  - "_atodbl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_atodbl-Funktion"
  - "_atoldbl_l-Funktion"
  - "atoflt-Funktion"
  - "atoflt_l-Funktion"
  - "atoldbl-Funktion"
  - "_atoldbl-Funktion"
  - "atodbl_l-Funktion"
  - "_atoflt_l-Funktion"
  - "atoldbl_l-Funktion"
  - "atodbl-Funktion"
  - "Zeichenfolgenkonvertierung, in Gleitkommawerte"
  - "_atoflt-Funktion"
  - "_atodbl_l-Funktion"
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# _atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge in einen double \(`_atodbl`\)\-, long double \(`_atoldbl`\)\- oder float \(`_atoflt`\)\-Wert.  
  
## Syntax  
  
```  
int _atodbl(  
   _CRT_DOUBLE * value,  
   char * str  
);  
int _atodbl_l (  
   _CRT_DOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoldbl(  
   _LDOUBLE * value,  
   char * str  
);  
int _atoldbl_l (  
   _LDOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoflt(  
   _CRT_FLOAT * value,  
   const char * str  
);  
int _atoflt_l(  
   _CRT_FLOAT * value,  
   const char * str,  
   locale_t locale  
);  
```  
  
#### Parameter  
 `value`  
 Der double\-, long double\- oder float\-Wert, der erstellt wird, indem die Zeichenfolge in einen Gleitkommawert konvertiert wird.  Diese Werte werden in eine Struktur eingeschlossen.  
  
 `str`  
 Die zu analysierende Zeichenfolge, die in einen Gleitkommawert konvertiert wird.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Gibt bei Erfolg 0 zurück.  Mögliche Fehlercodes sind `_UNDERFLOW` oder `_OVERFLOW`, die in der Headerdatei "Math.h" definiert werden.  
  
## Hinweise  
 Diese Funktionen konvertieren eine Zeichenfolge in einen Gleitkommawert.  Der Unterschied zwischen diesen Funktionen und der `atof`\-Familie der Funktionen ist der, dass diese Funktionen keinen Gleitkommacode generieren und keine Hardwareausnahmen verursachen.  Stattdessen werden Fehlerzustände als Fehlercodes gemeldet.  
  
 Wenn eine Zeichenfolge keine gültige Interpretation als Gleitkommawert aufweist, wird `value` auf 0 gesetzt und der Rückgabewert ist 0.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind identisch mit den Versionen, die keinen Suffix haben, verwenden jedoch den übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
## Anforderungen  
  
|Routinen|Erforderlicher Header|  
|--------------|---------------------------|  
|`_atodbl`, `_atoldbl`, `_atoflt`<br /><br /> `_atodbl_l`, `_atoldbl_l`, `_atoflt_l`|\<stdlib.h\>|  
  
## Beispiel  
  
```  
// crt_atodbl.c  
// Uses _atodbl to convert a string to a double precision  
// floating point value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main()  
{  
   char str1[256] = "3.141592654";  
   char abc[256] = "abc";  
   char oflow[256] = "1.0E+5000";  
   _CRT_DOUBLE dblval;  
   _CRT_FLOAT fltval;  
   int retval;  
  
   retval = _atodbl(&dblval, str1);  
  
   printf("Double value: %lf\n", dblval.x);  
   printf("Return value: %d\n\n", retval);  
  
   retval = _atoflt(&fltval, str1);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // A non-floating point value: returns 0.  
   retval = _atoflt(&fltval, abc);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // Overflow.  
   retval = _atoflt(&fltval, oflow);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   return 0;  
}  
```  
  
  **Double\-Wert: 3,141593**  
**Rückgabewert: 0**  
**Gleitkommawert: 3,141593**  
**Rückgabewert: 0**  
**Gleitkommawert: 0,000000**  
**Rückgabewert: 0**  
**Gleitkommawert: 1.\#INF00**  
**Rückgabewert: 3**   
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)