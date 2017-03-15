---
title: _mbsnbcat, _mbsnbcat_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbcat_l
- _mbsnbcat
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
- mbsnbcat
- mbsnbcat_l
- _mbsnbcat
- _mbsnbcat_l
dev_langs:
- C++
helpviewer_keywords:
- tcsncat_l function
- _tcsncat function
- mbsnbcat_l function
- mbsnbcat function
- _mbsnbcat_l function
- _tcsncat_l function
- _mbsnbcat function
- tcsncat function
ms.assetid: aa0f1d30-0ddd-48d1-88eb-c6884b20fd91
caps.latest.revision: 29
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 412e739b9a336cf98dcf08cba9a477625613cbfc
ms.lasthandoff: 02/24/2017

---
# <a name="mbsnbcat-mbsnbcatl"></a>_mbsnbcat, _mbsnbcat_l
Fügt höchstens die ersten `n` Bytes einer Multibyte-Zeichenfolge einer anderen Zeichenfolge an. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_mbsnbcat_s, _mbsnbcat_s_l](../../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char *_mbsnbcat(  
   unsigned char *dest,  
   const unsigned char *src,  
   size_t count   
);  
unsigned char *_mbsnbcat_l(  
   unsigned char *dest,  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
unsigned char *_mbsnbcat(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count   
); // C++ only  
template <size_t size>  
unsigned char *_mbsnbcat_l(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `dest`  
 Auf NULL endende Multibytezielzeichenfolge.  
  
 `src`  
 Auf NULL endende Multibytequellzeichenfolge.  
  
 `count`  
 Anzahl Bytes von `src`, die an `dest` angefügt werden.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 `_mbsnbcat` gibt einen Zeiger zur Zielzeichenfolge zurück. Kein Rückgabewert ist zur Fehleranzeige reserviert.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_mbsnbcat` fügt höchstens die ersten `count` Bytes von `src` an `dest` an. Wenn das Byte direkt vor dem Nullzeichen in `dest` ein führendes Byte ist, überschreibt das ursprüngliche Byte von `src` dieses führende Byte. Andernfalls überschreibt das ursprüngliche Byte von `src` das abschließende NULL-Zeichen von `dest`. Wenn ein Nullbyte in `src` auftritt, bevor `count` Bytes angefügt werden, fügt _`mbsnbcat` alle Bytes von `src` bis zu dem NULL-Zeichen an. Wenn `count` größer als die Länge von `src` ist, wird die Länge von `src` anstelle von `count` verwendet. Die resultierende Zeichenfolge wird mit einem NULL-Zeichen beendet. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die `_mbsnbcat`-Version der Funktion verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten. Die `_mbsnbcat_l`-Version ist beinahe identisch, verwendet jedoch stattdessen den ihr übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 **Sicherheitshinweis** Verwenden Sie eine mit NULL endende Zeichenfolge. Die mit NULL endende Zeichenfolge darf die Größe des Zielpuffers nicht überschreiten. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Wenn `dest` oder `src` `NULL` ist, generiert die Funktion einen Fehler wegen eines ungültigen Parameters, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn der Fehler behandelt wird, gibt die Funktion `EINVAL` zurück und legt `errno` auf `EINVAL` fest.  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsncat`|[strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|`_mbsnbcat`|[wcsncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|  
|`_tcsncat_l`|`_strncat_l`|`_mbsnbcat_l`|`_wcsncat_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_mbsnbcat`|\<mbstring.h>|  
|`_mbsnbcat_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](../../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)   
 [_mbsnbcpy, _mbsnbcpy_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [_mbsnbicmp, _mbsnbicmp_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [_mbsnbset, _mbsnbset_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [_mbsnbcat_s, _mbsnbcat_s_l](../../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md)
