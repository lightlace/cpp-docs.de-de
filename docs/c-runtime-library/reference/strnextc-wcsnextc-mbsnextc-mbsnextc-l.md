---
title: "_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strnextc"
  - "_mbsnextc_l"
  - "_mbsnextc"
  - "_wcsnextc"
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
  - "strnextc"
  - "tcsnextc"
  - "_mbsnextc_l"
  - "_mbsnextc"
  - "mbsnextc_l"
  - "ftcsnextc"
  - "mbsnextc"
  - "_tcsnextc"
  - "_wcsnextc"
  - "_ftcsnextc"
  - "_strnextc"
  - "wcsnextc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnextc-Funktion"
  - "_mbsnextc_l-Funktion"
  - "_strnextc-Funktion"
  - "_tcsnextc-Funktion"
  - "_wcsnextc-Funktion"
  - "mbsnextc-Funktion"
  - "mbsnextc_l-Funktion"
  - "strnextc-Funktion"
  - "tcsnextc-Funktion"
  - "wcsnextc-Funktion"
ms.assetid: e3086173-9eb5-4540-a23a-5d866bd05340
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sucht das nächste Zeichen in einer Zeichenfolge.  
  
> [!IMPORTANT]
>  `_mbsnextc` und `_mbsnextc_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
unsigned int _strnextc(  
   const char *str  
);  
unsigned int _wscnextc(  
   const wchar_t *str  
);   
unsigned int _mbsnextc(  
   const unsigned char *str   
);  
unsigned int _mbsnextc_l(  
   const unsigned char *str,  
   _locale_t locale  
);  
  
```  
  
#### Parameter  
 `str`  
 Quellzeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt den ganzzahligen Wert des nächsten Zeichens in `str` *zurück.*  
  
## Hinweise  
 Die `_mbsnextc`\-Funktion gibt den ganzzahligen Wert des folgenden Multibytezeichens in `str` zurück, ohne den Zeichenfolgenzeiger weiterzusetzen.  `_mbsnextc` erkennt Multibyte\-Zeichenfolgen gemäß der aktuellen [Multibyte\-Codepage](../../c-runtime-library/code-pages.md).  
  
 Wenn `str` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt 0 \(null\) zurück.  
  
 **Sicherheitshinweis** Diese API stellt eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar.  Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcsnextc`|`_strnextc`|`_mbsnextc`|`_wcsnextc`|  
  
 `_strnextc` und `_wcsnextc` sind Versionen von Einzelbytezeichenfolgen und Zeichenfolgen mit Breitzeichen von `_mbsnextc`.  `_wcsnextc` gibt den ganzzahligen Wert des folgenden Breitzeichens in `string` zurück. `_strnextc` gibt den ganzzahligen Wert des folgenden Einzelbytezeichens in `string` zurück.  `_strnextc` und `_wcsnextc` werden nur für diese Zuordnung bereitgestellt und sollten nicht für andere Zwecke verwendet werden.  Weitere Informationen finden Sie unter dem Thema zum [Verwenden von generischen Textzuordnungen](../../c-runtime-library/using-generic-text-mappings.md) und [Generische Textzuordnungen](../../c-runtime-library/generic-text-mappings.md).  
  
 `_mbsnextc_l` ist identisch, es werden den Parameter, der in stattdessen übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsnextc`|\<mbstring.h\>|  
|`_mbsnextc_l`|\<mbstring.h\>|  
|`_strnextc`|\<tchar.h\>|  
|`_wcsnextc`|\<tchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strdec, \_wcsdec, \_mbsdec, \_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strinc, \_wcsinc, \_mbsinc, \_mbsinc\_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [\_strninc, \_wcsninc, \_mbsninc, \_mbsninc\_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)