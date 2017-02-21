---
title: "isdigit, iswdigit, _isdigit_l, _iswdigit_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isdigit_l"
  - "iswdigit"
  - "_iswdigit_l"
  - "isdigit"
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
  - "_iswdigit_l"
  - "_isdigit_l"
  - "iswdigit"
  - "isdigit"
  - "_istdigit"
  - "_istdigit_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iswdigit-Funktion"
  - "iswdigit_l-Funktion"
  - "_iswdigit_l-Funktion"
  - "_istdigit_l-Funktion"
  - "_istdigit-Funktion"
  - "istdigit-Funktion"
  - "isdigit-Funktion"
  - "isdigit_l-Funktion"
  - "_ismbcdigit_l-Funktion"
  - "_isdigit_l-Funktion"
ms.assetid: 350b0093-843a-47b0-954e-c1776e8a3853
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# isdigit, iswdigit, _isdigit_l, _iswdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob eine ganze Zahl ein Dezimalstellenzeichen darstellt.  
  
## Syntax  
  
```  
int isdigit(   
   int c   
);  
int iswdigit(   
   wint_t c   
);  
int _isdigit_l(   
   int c,  
   _locale_t locale  
);  
int _iswdigit_l(   
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
 Jede dieser Routinen gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine bestimmte Darstellung eines Dezimalstellenzeichens ist.  `isdigit` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine Dezimalstelle ist \(0 \- 9\).  `iswdigit` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein Breitzeichen ist, das einem Dezimalstellenzeichen entspricht.  Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix verwenden das übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Das Verhalten von `isdigit` und `_isdigit_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt.  Wenn eine CRT\-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_istdigit`|`isdigit`|[\_ismbcdigit](../../c-runtime-library/reference/ismbcalnum-functions.md)|`iswdigit`|  
|`_istdigit_l`|`_isdigit_l`|[\_ismbcdigit\_l](../../c-runtime-library/reference/ismbcalnum-functions.md)|`_iswdigit_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`isdigit`|\<ctype.h\>|  
|`iswdigit`|\<ctype.h\> oder \<wchar.h\>|  
|`_isdigit_l`|\<ctype.h\>|  
|`_iswdigit_l`|\<ctype.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 [System::Char::IsDigit](https://msdn.microsoft.com/en-us/library/system.char.isdigit.aspx)  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)