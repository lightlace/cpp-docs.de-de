---
title: wctomb_s, _wctomb_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_s_l
- wctomb_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctomb_s
- _wctomb_s_l
dev_langs:
- C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: ac97c0bc957c28d8d0837199157d52d4ac0536e1
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="wctombs-wctombsl"></a>wctomb_s, _wctomb_s_l
Konvertiert ein Breitzeichen in das entsprechende Multibytezeichen. Eine Version von [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) mit Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pRetValue`  
 Die Anzahl von Bytes oder ein Code, der das Ergebnis angibt.  
  
 [out] `mbchar`  
 Die Adresse eines Multibytezeichens.  
  
 [in] `sizeInBytes`  
 Größe des `mbchar`-Puffers.  
  
 [in] `wchar`  
 Ein Breitzeichen.  
  
 [in] `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
 Fehlerbedingungen  
  
|`mbchar`|`sizeInBytes`|Rückgabewert|`pRetValue`|  
|--------------|-------------------|------------------|-----------------|  
|`NULL`|>0|`EINVAL`|nicht geändert|  
|alle|>`INT_MAX`|`EINVAL`|nicht geändert|  
|any|zu klein|`EINVAL`|nicht geändert|  
  
 Wenn eine der oben genannten Fehlerbedingungen auftritt, wird ein Handler für ungültige Parameter aufgerufen (siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md)). Wenn die weitere Ausführung zugelassen wird, gibt `wctomb` `EINVAL` zurück und setzt `errno` auf `EINVAL`.  
  
## <a name="remarks"></a>Hinweise  
 Die `wctomb_s`-Funktion konvertiert das `wchar`-Argument in das entsprechende Multibytezeichen und speichert das Ergebnis in `mbchar`. Sie können die Funktion von einem beliebigen Punkt in einem beliebigen Programm aufrufen.  
  
 Wenn `wctomb_s` das Breitzeichen in ein Multibytezeichen konvertiert, wird die Anzahl von Bytes (die nie größer als `MB_CUR_MAX` ist) im Breitzeichen in den Integer geschrieben, auf den von `pRetValue` gezeigt wird. Wenn `wchar` das Breitzeichen NULL (L'\0') ist, füllt `wctomb_s` `pRetValue` mit 1. Wenn der Zielzeiger `mbchar` NULL ist, schreibt `wctomb_s` 0 in `pRetValue`. Wenn die Konvertierung nicht möglich, im aktuellen Gebietsschema ist `wctomb_s` setzt-1 in `pRetValue`.  
  
 `wctomb_s` verwendet das aktuelle Gebietsschema für jedes Verhalten, das vom Gebietsschema abhängig ist; `_wctomb_s_l` ist identisch, nur dass sie stattdessen das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`wctomb_s`|\<stdlib.h>|  
|`_wctomb_s_l`|\<stdlib.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Dieses Programm stellt das Verhalten der Funktion `wctomb` dar.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
