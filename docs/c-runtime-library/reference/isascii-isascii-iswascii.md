---
title: "Isascii, __isascii, iswascii"
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
  - "iswascii"
  - "__isascii"
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
  - "iswascii"
  - "istascii"
  - "__isascii"
  - "_istascii"
  - "isascii"
  - "ctype/isascii"
  - "ctype/__isascii"
  - "corecrt_wctype/iswascii"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__isascii-Funktion"
  - "_isascii-Funktion"
  - "isascii-Funktion"
  - "_istascii-Funktion"
  - "istascii-Funktion"
  - "iswascii-Funktion"
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# Isascii, __isascii, iswascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein bestimmtes Zeichen mit ASCII\-Zeichen ist.  
  
## Syntax  
  
```  
int __isascii(   
   int c   
);  
int iswascii(   
   wint_t c   
);  
#define isascii __isascii  
```  
  
#### Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
## Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich NULL, wenn `c` eine bestimmte Darstellung von ASCII\-Zeichen.`__isascii` Gibt einen Wert ungleich NULL zurück, wenn `c` wird ein ASCII\-Zeichen \(im Bereich 0 x 00 – 0x7F\).`iswascii` Gibt einen Wert ungleich NULL zurück, wenn `c` ist eine Breitzeichen\-Darstellung von ASCII\-Zeichen. Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
## Hinweise  
 Beide `__isascii` und `iswascii` werden als Makros implementiert, es sei denn, die \_CTYPE\_DISABLE\_MACROS Präprozessormakro definiert ist.  
  
 Für die Abwärtskompatibilität `isascii` wird als nur, wenn ein Makro implementiert [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) ist nicht definiert oder wird definiert als 0; andernfalls ist es nicht definiert.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`isascii`, `__isascii`|C: \< ctype.h \><br /><br /> C\+\+: \< Cctype \> oder \< ctype.h \>|  
|`iswascii`|C: \< wctype.h \>, \< ctype.h \>, oder \< wchar.h \><br /><br /> C\+\+: \< Cwctype \>, \< Cctype \>, \< wctype.h \>, \< ctype.h \>, oder \< wchar.h \>|  
  
 Die `isascii`, `__isascii` und `iswascii` Funktionen sind Microsoft\-spezifisch. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)