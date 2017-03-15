---
title: "islower, iswlower, _islower_l, _iswlower_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswlower"
  - "_islower_l"
  - "islower"
  - "_iswlower_l"
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
  - "_istlower"
  - "islower"
  - "_ismbclower_l"
  - "_liswlower_l"
  - "_istlower_l"
  - "_iswlower_l"
  - "_islower _l"
  - "_islower_l"
  - "iswlower"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_islower _l-Funktion"
  - "_islower_l-Funktion"
  - "_ismbclower_l-Funktion"
  - "_istlower-Funktion"
  - "_istlower_l-Funktion"
  - "_iswlower_l-Funktion"
  - "_liswlower_l-Funktion"
  - "islower-Funktion"
  - "istlower-Funktion"
  - "iswlower-Funktion"
ms.assetid: fcc3b70a-2b47-45fd-944d-e5c1942e6457
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# islower, iswlower, _islower_l, _iswlower_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob eine ganze Zahl einen Kleinbuchstaben darstellt.  
  
## Syntax  
  
```  
int islower(  
   int c   
);  
int iswlower(  
   wint_t c   
);  
int islower_l(  
   int c,  
   _locale_t locale  
);  
int _iswlower_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine bestimmte Darstellung eines Zeichens in Kleinbuchstaben ist.  `islower` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein Kleinbuchstabe \(a–z\) ist.  `iswlower` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein Breitzeichen ist, das einem Kleinbuchstaben entspricht, oder wenn `c` ein von der Implementierung abhängiger Breitzeichensatz ist, in dem weder `iswcntrl`, `iswdigit`, `iswpunct` noch `iswspace` ungleich 0 \(null\) ist.  Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix verwenden das übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Das Verhalten von `islower` und `_islower_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt.  Wenn eine CRT\-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_istlower`|`islower`|[\_ismbclower](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`iswlower`|  
|`_istlower_l`|`_islower _l`|[\_ismbclower\_l](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`_liswlower_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`islower`|\<ctype.h\>|  
|`iswlower`|\<ctype.h\> oder \<wchar.h\>|  
|`_islower_l`|\<ctype.h\>|  
|`_swlower_l`|\<ctype.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 [System::Char::IsLower](https://msdn.microsoft.com/en-us/library/system.char.islower.aspx)  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)