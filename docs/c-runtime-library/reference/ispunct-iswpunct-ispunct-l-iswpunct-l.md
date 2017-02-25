---
title: "ispunct, iswpunct, _ispunct_l, _iswpunct_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ispunct"
  - "_iswpunct_l"
  - "iswpunct"
  - "_ispunct_l"
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
  - "iswpunct"
  - "_istpunct"
  - "ispunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ispunct_l-Funktion"
  - "_istpunct-Funktion"
  - "_iswpunct_l-Funktion"
  - "ispunct-Funktion"
  - "ispunct_l-Funktion"
  - "istpunct-Funktion"
  - "iswpunct-Funktion"
  - "iswpunct_l-Funktion"
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# ispunct, iswpunct, _ispunct_l, _iswpunct_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob eine ganze Zahl ein Interpunktionszeichen darstellt.  
  
## Syntax  
  
```  
int ispunct(  
   int c   
);  
int iswpunct(  
   wint_t c   
);  
int _ispunct_l(  
   int c,  
   _locale_t locale  
);  
int _iswpunct_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine bestimmte Darstellung eines Interpunktionszeichens ist.  `ispunct` gibt einen Wert ungleich 0 \(null\) für jedes druckbare Zeichen zurück, das kein Leerzeichen oder ein Zeichen ist, bei dem `isalnum` ungleich 0 \(null\) ist.  `iswpunct` gibt einen Wert ungleich 0 \(null\) für jedes druckbare Breitzeichen zurück, das weder das Leerzeichenbreitzeichen noch ein Breitzeichen ist, bei dem `iswalnum` ungleich 0 ist.  Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
 Das Ergebnis der Testbedingung für die `ispunct`\-Funktionen hängt von der `LC_CTYPE` Kategorieneinstellung des Gebietsschemas ab. Weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen, die das `_l`\-Suffix nicht verwenden, verwenden das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Das Verhalten von `ispunct` und `_ispunct_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt.  Wenn eine CRT\-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|**\_** `istpunct`|`ispunct`|[\_ismbcpunct](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswpunct`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`ispunct`|\<ctype.h\>|  
|`iswpunct`|\<ctype.h\> oder \<wchar.h\>|  
|`_ispunct_l`|\<ctype.h\>|  
|`_iswpunct_l`|\<ctype.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)