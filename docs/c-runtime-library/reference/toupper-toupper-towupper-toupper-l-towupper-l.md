---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towupper
- _toupper
- _totupper
- toupper
dev_langs: C++
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0414cd211cb9b833f24d2aac9ad9a82758c4efcf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l
Zeichen in Großbuchstaben konvertieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu konvertierendes Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Routinen konvertiert eine Kopie von `c`, wenn die Konvertierung möglich ist, und gibt das Ergebnis zurück.  
  
 Wenn `c` ein Breitzeichen ist, für das `iswlower` ungleich null ist und es ein entsprechendes Breitzeichen gibt, für das `iswupper` ungleich null ist, gibt `towupper` das entsprechende Breitzeichen zurück, andernfalls gibt `towupper` `c` unverändert zurück.  
  
 Es ist kein Rückgabewert zur Fehleranzeige reserviert.  
  
 Damit `toupper` die erwarteten Ergebnisse liefert, müssen [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) und [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md) beide ungleich null zurückgeben.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Routinen konvertiert einen vorhandenen Kleinbuchstaben in einen Großbuchstaben, wenn dies möglich und relevant ist. Die Konvertierung von `towupper` ist gebietsschemaspezifisch. Es werden nur die für das aktuelle Gebietsschema relevanten Zeichen geändert. Die Funktionen ohne das Suffix `_l` verwenden das aktuelle Gebietsschema. Die Versionen dieser Funktionen mit dem Suffix `_l` übernehmen das Gebietsschema als Parameter und verwenden diesen anstatt des aktuellen Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Damit `toupper` die erwarteten Ergebnisse liefert, müssen [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) und [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) beide ungleich null zurückgeben.  
  
 [Datenkonvertierungsroutinen](../../c-runtime-library/data-conversion.md)  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  `_toupper_l` und `_towupper_l` haben keine Gebietsschemaabhängigkeit und sind nicht für den direkten Aufruf vorgesehen. Sie werden zur internen Verwendung von `_totupper_l` bereitgestellt.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`toupper`|\<ctype.h>|  
|`_toupper`|\<ctype.h>|  
|`towupper`|\<ctype.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel in [to-Funktionen](../../c-runtime-library/to-functions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [is- und isw-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [to-Funktionen](../../c-runtime-library/to-functions.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)