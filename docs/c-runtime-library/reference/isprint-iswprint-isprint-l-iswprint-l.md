---
title: "isprint, iswprint, _isprint_l, _iswprint_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswprint"
  - "isprint"
  - "_isprint_l"
  - "_iswprint_l"
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
  - "iswprint"
  - "_istprint"
  - "isprint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_isprint_l-Funktion"
  - "_istprint-Funktion"
  - "_iswprint_l-Funktion"
  - "isprint-Funktion"
  - "isprint_l-Funktion"
  - "istprint-Funktion"
  - "iswprint-Funktion"
  - "iswprint_l-Funktion"
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# isprint, iswprint, _isprint_l, _iswprint_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob eine ganze Zahl ein druckbares Zeichen darstellt.  
  
## Syntax  
  
```  
int isprint(  
   int c   
);  
int iswprint(  
   wint_t c   
);  
int _isprint_l(  
   int c,  
   _locale_t locale  
);  
int _iswprint_l(  
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
 Jede dieser Routinen gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine bestimmte Darstellung eines druckbaren Zeichens ist.  `isprint` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein druckbares Zeichen ist. Dazu gehört auch das Leerzeichen \(0x20 \- 0x7E\).  `iswprint` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein druckbares Breitzeichen ist. Dazu gehört auch das breite Leerzeichen.  Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
 Das Ergebnis der Testbedingung für diese Funktionen hängt von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas ab. Weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen, die das `_l`\-Suffix nicht verwenden, verwenden das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Das Verhalten von `isprint` und `_isprint_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt.  Wenn eine CRT\-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_unicode definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|**\_** `istprint`|`isprint`|[\_ismbcprint](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswprint`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`isprint`|\<ctype.h\>|  
|`iswprint`|\<ctype.h\> oder \<wchar.h\>|  
|`_isprint_l`|\<ctype.h\>|  
|`_iswprint_l`|\<ctype.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)