---
title: "Iscsym, Iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l"
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
  - "_iswcsym_l"
  - "__iswcsym"
  - "__iscsym"
  - "_iswcsymf_l"
  - "_iscsym_l"
  - "__iswcsymf"
  - "__iscsymf"
  - "_iscsymf_l"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_iswcsym_l"
  - "_iswcsymf_l"
  - "iscsymf"
  - "iswcsymf"
  - "__iswcsym"
  - "__iswcsymf"
  - "iscsym"
  - "iswcsym"
  - "__iscsym"
  - "_iscsym_l"
  - "_iscsymf_l"
  - "__iscsymf"
  - "ctype/iscsym"
  - "ctype/iscsymf"
  - "ctype/__iscsym"
  - "ctype/__iscsymf"
  - "ctype/__iscsym_l"
  - "ctype/__iscsymf_l"
  - "ctype/__iswcsym"
  - "ctype/__iswcsymf"
  - "ctype/__iswcsym_l"
  - "ctype/__iswcsymf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "iscsymf_l-Funktion"
  - "iswsym_l-Funktion"
  - "_iswcsym_l-Funktion"
  - "iscsym_l-Funktion"
  - "_iscsymf_l-Funktion"
  - "_iswcsymf_l-Funktion"
  - "_iscsym_l-Funktion"
  - "__iscsym-Funktion"
  - "__iswcsymf-Funktion"
  - "iswsymf_l-Funktion"
  - "__iscsymf-Funktion"
  - "__iswcsym-Funktion"
  - "iscsym-Funktion"
  - "iscsymf-Funktion"
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# Iscsym, Iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob eine ganze Zahl ein Zeichen darstellt, die in einem Bezeichner verwendet werden kann.  
  
## Syntax  
  
```  
int __iscsym(   
   int c   
);  
int __iswcsym(   
   wint_t c   
);  
int __iscsymf(   
   int c   
);  
int __iswcsymf(   
   wint_t c   
);  
int _iscsym_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsym_l(   
   wint_t c,  
   _locale_t locale  
);  
int _iscsymf_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsymf_l(   
   wint_t c,  
   _locale_t locale  
);  
#define iscsym __iscsym  
#define iscsymf __iscsymf  
```  
  
#### Parameter  
 `c`  
 Zu testende ganze Zahl.`c` sollte im Bereich von 0 bis 255, für die schmalen Version der Funktion.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Beide `__iscsym` und `__iswcsym` einen Wert ungleich NULL zurück, wenn `c` ist ein Buchstabe, Unterstrich oder Ziffer. Beide `__iscsymf` und `__iswcsymf` einen Wert ungleich NULL zurück, wenn `c` ein Buchstabe oder Unterstrich. Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt. Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch das ihnen übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Hinweise  
 Diese Routinen werden als Makros definiert, es sei denn, die \_CTYPE\_DISABLE\_MACROS Präprozessormakro definiert ist. Wenn Sie die makroversionen dieser Routinen verwenden, können mehr als einmal die Argumente ausgewertet werden. Seien Sie vorsichtig, wenn Sie Ausdrücke mit Nebeneffekte in der Argumentliste verwendet werden.  
  
 Um Abwärtskompatibilität zu gewährleisten `iscsym` und `iscsymf` sind definiert als Makros nur, wenn [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) ist nicht definiert oder wird definiert als 0; andernfalls sind sie nicht definiert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, `_iswcsymf_l`|C: \< ctype.h \><br /><br /> C\+\+: \< Cctype \> oder \< ctype.h \>|  
  
 Die `iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, und `_iswcsymf_l` Routinen sind Microsoft\-spezifisch. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)