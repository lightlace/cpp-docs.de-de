---
title: "_strninc, _wcsninc, _mbsninc, _mbsninc_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsninc"
  - "_mbsninc_l"
  - "_wcsninc"
  - "_strninc"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strninc"
  - "wcsninc"
  - "mbsninc_l"
  - "_strninc"
  - "_tcsninc"
  - "mbsninc"
  - "_mbsninc_l"
  - "_ftcsninc"
  - "_wcsninc"
  - "_mbsninc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsninc-Funktion"
  - "_mbsninc_l-Funktion"
  - "_strninc-Funktion"
  - "_tcsninc-Funktion"
  - "_wcsninc-Funktion"
  - "mbsninc-Funktion"
  - "mbsninc_l-Funktion"
  - "strninc-Funktion"
  - "tcsninc-Funktion"
  - "wcsninc-Funktion"
ms.assetid: 6caace64-f9e4-48c0-afa8-ea51824ad723
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _strninc, _wcsninc, _mbsninc, _mbsninc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versetzt den Zeichenfolgenzeiger um `n` Zeichen nach vorn.  
  
> [!IMPORTANT]
>  `_mbsninc` und `_mbsninc_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *_strninc(  
   const char *str,  
   size_t count   
);  
wchar_t *_wcsninc(  
   const wchar_t *str,  
   size_t count   
);  
unsigned char *_mbsninc(  
   const unsigned char *str,  
   size_t count   
);  
unsigned char *_mbsninc(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `str`  
 Quellzeichenfolge.  
  
 `count`  
 Anzahl der Zeichen zum Erhöhen eines Zeichenfolgenzeigers.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen gibt einen Zeiger auf `str` zurück, nachdem `str` um `count` Zeichen erhöht wurde, oder gibt `NULL` zurück, wenn der angegebene Zeiger `NULL` ist.  Wenn `count` größer oder gleich der Anzahl von Zeichen in `str` ist, ist das Ergebnis nicht definiert.  
  
## Hinweise  
 Die `_mbsninc`\-Funktion erhöht `str` um `count` Multibytezeichen.  `_mbsninc` erkennt Multibyte\-Zeichenfolgen gemäß der aktuellen [Multibyte\-Codepage](../../c-runtime-library/code-pages.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcsninc`|`_strninc`|`_mbsninc`|`_wcsninc`|  
  
 `_strninc` und `_wcsninc` sind Versionen von Einzelbytezeichenfolgen und Zeichenfolgen mit Breitzeichen von `_mbsninc`.  `_wcsninc` und `_strninc` werden nur für diese Zuordnung bereitgestellt und sollten nicht für andere Zwecke verwendet werden.  Weitere Informationen finden Sie unter dem Thema zum [Verwenden von generischen Textzuordnungen](../../c-runtime-library/using-generic-text-mappings.md) und [Generische Textzuordnungen](../../c-runtime-library/generic-text-mappings.md).  
  
 `_mbsninc_l` ist nahezu identisch, verwendet jedoch stattdessen den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsninc`|\<mbstring.h\>|  
|`_mbsninc_l`|\<mbstring.h\>|  
|`_strninc`|\<tchar.h\>|  
|`_wcsninc`|\<tchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strdec, \_wcsdec, \_mbsdec, \_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strinc, \_wcsinc, \_mbsinc, \_mbsinc\_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [\_strnextc, \_wcsnextc, \_mbsnextc, \_mbsnextc\_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)