---
title: _mbsnbcat_s, _mbsnbcat_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbcat_s_l
- _mbsnbcat_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
dev_langs: C++
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7288c00de4f09175d7fffd816267201011892953
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mbsnbcats-mbsnbcatsl"></a>_mbsnbcat_s, _mbsnbcat_s_l
Wird an eine Multibytezeichen-Zeichenfolge angefügt. Es handelt sich hierbei höchstens um die ersten `n` Byte einer anderen Multibytezeichen-Zeichenfolge. Dies sind Versionen von [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md), enthalten aber Sicherheitserweiterungen wie unter [Sicherheitsfunktionen im CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `dest`  
 Auf NULL endende Multibytezielzeichenfolge.  
  
 `sizeInBytes`  
 Größe des `dest`-Puffers in Byte.  
  
 `src`  
 Auf NULL endende Multibytequellzeichenfolge.  
  
 `Count`  
 Anzahl Bytes von `src`, die an `dest` angefügt werden.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, andernfalls ein Fehlercode.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`Dest`|`sizeInBytes`|`src`|Rückgabewert|  
|------------|-------------------|-----------|------------------|  
|`NULL`|any|any|`EINVAL`|  
|Beliebig|<= 0|any|`EINVAL`|  
|Beliebig|any|`NULL`|`EINVAL`|  
  
 Wenn eine dieser Fehlerbedingungen auftritt, generiert die Funktion einen Fehler über ungültige Parameter, wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn der Fehler behandelt wird, gibt die Funktion `EINVAL` zurück und legt `errno` auf `EINVAL` fest.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_mbsnbcat_s` fügt höchstens die ersten `dest` Bytes von `count` an `src` an. Wenn das Byte, das dem null-Zeichen in `dest` unmittelbar vorangestellt ist, ein führendes Byte ist, wird es durch das Anfangsbyte von `src` überschrieben. Andernfalls überschreibt das ursprüngliche Byte von `src` das abschließende NULL-Zeichen von `dest`. Wenn ein Nullbyte in `src` auftritt, bevor `count` Bytes angefügt werden, fügt `_mbsnbcat_s` alle Bytes von `src` bis zu dem NULL-Zeichen an. Wenn `count` größer als die Länge von `src` ist, wird die Länge von `src` anstelle von `count` verwendet. Die resultierende Zeichenfolge wird durch ein NULL-Zeichen beendet. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne das `_l`-Suffix das aktuelle Gebietsschema verwenden, und diejenigen mit `_l`-Suffix den übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht. Die Überladungen können automatisch Rückschlüsse über die Pufferlänge ziehen, wodurch kein „size“-Argument angegeben werden muss. Zudem können sie automatisch ihre neueren und sichereren Funktionen zum Ersetzen von älteren, unsichereren Funktionen verwenden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsncat`|[strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|`_mbsnbcat_s`|[wcsncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|  
|`_tcsncat_s_l`|`_strncat_s_l`|`_mbsnbcat_s_l`|`_wcsncat_s_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_mbsnbcat_s`|\<mbstring.h>|  
|`_mbsnbcat_s_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](../../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)   
 [_mbsnbcpy, _mbsnbcpy_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [_mbsnbcpy_s, _mbsnbcpy_s_l](../../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)   
 [_mbsnbset, _mbsnbset_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)