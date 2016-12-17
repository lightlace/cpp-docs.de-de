---
title: "_strinc, _wcsinc, _mbsinc, _mbsinc_l"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mbsinc"
  - "_wcsinc"
  - "_mbsinc_l"
  - "_strinc"
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
  - "mbsinc_l"
  - "_strinc"
  - "strinc"
  - "_mbsinc"
  - "_wcsinc"
  - "wcsinc"
  - "mbsinc"
  - "_mbsinc_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsinc-Funktion"
  - "_mbsinc_l-Funktion"
  - "_strinc-Funktion"
  - "_tcsinc-Funktion"
  - "_wcsinc-Funktion"
  - "mbsinc-Funktion"
  - "mbsinc_l-Funktion"
  - "strinc-Funktion"
  - "tcsinc-Funktion"
  - "wcsinc-Funktion"
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# _strinc, _wcsinc, _mbsinc, _mbsinc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versetzt einen Zeichenfolgenzeiger um ein Zeichen nach vorn.  
  
> [!IMPORTANT]
>  `_mbsinc` und `_mbsinc_l` können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *_strinc(    const char *current,    _locale_t locale ); wchar_t *_wcsinc(    const wchar_t *current,    _locale_t locale ); unsigned char *_mbsinc(    const unsigned char *current  ); unsigned char *_mbsinc_l(    const unsigned char *current,    _locale_t locale );   
```  
  
#### Parameter  
 `current`  
 Zeichenzeiger.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen gibt einen Zeiger auf Zeichen zurück, das unmittelbar auf `current` folgt.  
  
## Hinweise  
 Die `_mbsinc`\-Funktion gibt einen Zeiger auf das erste Byte des Multibytezeichens zurück, das unmittelbar auf `current` folgt.  `_mbsinc` erkennt Multibytezeichensequenzen gemäß der derzeit verwendeten [Multibyte\-Codepage](../../c-runtime-library/code-pages.md). `_mbsinc_l` ist nahezu identisch, verwendet jedoch stattdessen den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Die in in Tchar.h definierte generische Textfunktion `_tcsinc` wird zu `_mbsinc` zugeordnet, wenn `_MBCS` definiert ist, oder zu `_wcsinc`, wenn `_UNICODE` definiert ist.  Andernfalls wird `_tcsinc` `_strinc` zugeordnet.  `_strinc` und `_wcsinc` sind Einzelbytezeichen\- und Breitzeichenversionen von `_mbsinc`.  `_strinc` und `_wcsinc` werden nur für diese Zuordnung bereitgestellt und sollten nicht für andere Zwecke verwendet werden.  Weitere Informationen finden Sie unter [Verwenden von Zuordnungen für generischen Text](../../c-runtime-library/using-generic-text-mappings.md) und [Zuordnungen für generischen Text](../../c-runtime-library/generic-text-mappings.md).  
  
 Wenn `current` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `EINVAL` zurück und stellt `errno` auf `EINVAL` ein.  
  
> [!IMPORTANT]
>  Diese Funktionen sind möglicherweise für Pufferüberlaufrisiken anfällig.  Pufferüberläufe können für Systemangriffe eingesetzt werden, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsinc`|\<mbstring.h\>|  
|`_mbsinc_l`|\<mbstring.h\>|  
|`_strinc`|\<tchar.h\>|  
|`_wcsinc`|\<tchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strdec, \_wcsdec, \_mbsdec, \_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strnextc, \_wcsnextc, \_mbsnextc, \_mbsnextc\_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [\_strninc, \_wcsninc, \_mbsninc, \_mbsninc\_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)