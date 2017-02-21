---
title: "_mbsnbcat_s, _mbsnbcat_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbcat_s_l"
  - "_mbsnbcat_s"
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
  - "_mbsnbcat_s"
  - "mbsnbcat_s"
  - "_mbsnbcat_s_l"
  - "mbsnbcat_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcat_s-Funktion"
  - "_mbsnbcat_s_l-Funktion"
  - "_tcsncat-Funktion"
  - "_tcsncat_s_l-Funktion"
  - "mbsnbcat_s-Funktion"
  - "mbsnbcat_s_l-Funktion"
  - "tcsncat-Funktion"
  - "tcsncat_s_l-Funktion"
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _mbsnbcat_s, _mbsnbcat_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird an eine Multibytezeichen\-Zeichenfolge angefügt. Es handelt sich hierbei höchstens um die ersten `n` Byte einer anderen Multibytezeichen\-Zeichenfolge.  Dies sind Versionen von [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md), enthalten aber Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
errno_t _mbsnbcat_s(  
   unsigned char *dest,  
   size_t sizeInBytes,  
   const unsigned char *src,  
   size_t count   
);  
errno_t _mbsnbcat_s_l(  
   unsigned char *dest,  
   size_t sizeInBytes,  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbcat_s(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbcat_s_l(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `dest`  
 Auf NULL endende Multibytezielzeichenfolge.  
  
 `sizeInBytes`  
 Größe des `dest`\-Puffers in Byte.  
  
 `src`  
 Auf NULL endende Multibytequellzeichenfolge.  
  
 `Count`  
 Anzahl Bytes von `src`, die an `dest` angefügt werden.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Null, wenn erfolgreich, andernfalls ein Fehlercode.  
  
### Fehlerbedingungen  
  
|`Dest`|`sizeInBytes`|`src`|Rückgabewert|  
|------------|-------------------|-----------|------------------|  
|`NULL`|alle|alle|`EINVAL`|  
|Beliebig|\<\= 0|alle|`EINVAL`|  
|Beliebig|alle|`NULL`|`EINVAL`|  
  
 Wenn eine dieser Fehlerbedingungen auftritt, generiert die Funktion einen Fehler über ungültige Parameter, wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.  Wenn der Fehler behandelt wird, gibt die Funktion `EINVAL` zurück und legt `errno` auf `EINVAL` fest.  
  
## Hinweise  
 Die Funktion `_mbsnbcat_s` fügt höchstens die ersten `dest` Bytes von `count` an `src` an.  Wenn das Byte, das dem null\-Zeichen in `dest` unmittelbar vorangestellt ist, ein führendes Byte ist, wird es durch das Anfangsbyte von `src` überschrieben.  Andernfalls überschreibt das ursprüngliche Byte von `src` das abschließende NULL\-Zeichen von `dest`.  Wenn ein Nullbyte in `src` auftritt, bevor `count` Bytes angefügt werden, fügt `_mbsnbcat_s` alle Bytes von `src` bis zu dem NULL\-Zeichen an.  Wenn `count` größer als die Länge von `src` ist, wird die Länge von `src` anstelle von `count` verwendet.  Die resultierende Zeichenfolge wird durch ein NULL\-Zeichen beendet.  Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne das `_l`\-Suffix das aktuelle Gebietsschema verwenden, und diejenigen mit `_l`\-Suffix den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht. Die Überladungen können automatisch Rückschlüsse über die Pufferlänge ziehen, wodurch kein „size“\-Argument angegeben werden muss. Zudem können sie automatisch ihre neueren und sichereren Funktionen zum Ersetzen von älteren, unsichereren Funktionen verwenden.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf.  Um dieses Verhalten zu deaktivieren, verwenden Sie [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tcsncat`|[strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|`_mbsnbcat_s`|[wcsncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|  
|`_tcsncat_s_l`|`_strncat_s_l`|`_mbsnbcat_s_l`|`_wcsncat_s_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsnbcat_s`|\<mbstring.h\>|  
|`_mbsnbcat_s_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_strncnt, \_wcsncnt, \_mbsnbcnt, \_mbsnbcnt\_l, \_mbsnccnt, \_mbsnccnt\_l](../../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)   
 [\_mbsnbcpy, \_mbsnbcpy\_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [\_mbsnbcpy\_s, \_mbsnbcpy\_s\_l](../../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)   
 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)