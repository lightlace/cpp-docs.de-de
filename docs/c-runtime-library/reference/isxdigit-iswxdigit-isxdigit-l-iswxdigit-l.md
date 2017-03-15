---
title: "isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_iswxdigit_l"
  - "iswxdigit"
  - "isxdigit"
  - "_isxdigit_l"
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
  - "iswxdigit"
  - "isxdigit"
  - "_istxdigit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_istxdigit-Funktion"
  - "_iswxdigit_l-Funktion"
  - "_isxdigit_l-Funktion"
  - "Hexadezimalzeichen"
  - "istxdigit-Funktion"
  - "iswxdigit-Funktion"
  - "iswxdigit_l-Funktion"
  - "isxdigit-Funktion"
  - "isxdigit_l-Funktion"
ms.assetid: c8bc5146-0b58-4e3f-bee3-f2318dd0f829
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob eine ganze Zahl ein Zeichen darstellt, das eine Hexadezimalziffer ist.  
  
## Syntax  
  
```  
int isxdigit(  
   int c   
);  
int iswxdigit(  
   wint_t c   
);  
int _isxdigit_l(  
   int c,  
   _locale_t locale  
);  
int _iswxdigit_l(  
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
 Jede dieser Routinen gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine bestimmte Darstellung einer Hexadezimalziffer ist.  `isxdigit` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` eine Hexadezimalziffer ist \(A–F, a–f oder 0–9\).  `iswxdigit` gibt einen Wert ungleich 0 \(null\) zurück, wenn `c` ein Breitzeichen ist, das einem Hexadezimalziffernzeichen entspricht.  Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
 Für das Gebietsschema "C " unterstützt die `iswxdigit`\-Funktion keine Unicode\-Hexadezimalzeichen voller Breite.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix verwenden das übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Das Verhalten von `isxdigit` und `_isxdigit_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt.  Wenn eine CRT\-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_istxdigit`|`isxdigit`|`isxdigit`|`iswxdigit`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`isxdigit`|\<ctype.h\>|  
|`iswxdigit`|\<ctype.h\> oder \<wchar.h\>|  
|`_isxdigit_l`|\<ctype.h\>|  
|`_iswxdigit_l`|\<ctype.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 [System::Char::IsNumber](https://msdn.microsoft.com/en-us/library/system.char.isnumber.aspx)  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)