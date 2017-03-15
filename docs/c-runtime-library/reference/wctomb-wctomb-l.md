---
title: wctomb, _wctomb_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_l
- wctomb
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
- wctomb
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
caps.latest.revision: 23
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
ms.openlocfilehash: 3d95aae18858582f732459e136c998c15d70189e
ms.lasthandoff: 02/24/2017

---
# <a name="wctomb-wctombl"></a>wctomb, _wctomb_l
Konvertiert ein Breitzeichen in das entsprechende Multibytezeichen. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mbchar`  
 Die Adresse eines Multibytezeichens.  
  
 `wchar`  
 Ein Breitzeichen.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn `wctomb` das Breitzeichen in ein Multibytezeichen konvertiert, wird die Anzahl von Bytes (die nie größer als `MB_CUR_MAX` ist) im Breitzeichen zurückgegeben. Wenn `wchar` das Breitzeichen NULL (L'\0') ist, gibt `wctomb` 1 zurück. Wenn der Zielzeiger `mbchar` NULL ist, gibt `wctomb` 0 zurück. Wenn die Konvertierung im aktuellen Gebietsschema nicht möglich ist, gibt `wctomb` -1 zurück, und `errno` wird auf `EILSEQ` festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die `wctomb`-Funktion konvertiert das `wchar`-Argument in das entsprechende Multibytezeichen und speichert das Ergebnis in `mbchar`. Sie können die Funktion von einem beliebigen Punkt in einem beliebigen Programm aufrufen. `wctomb` verwendet das aktuelle Gebietsschema für jedes Verhalten, das vom Gebietsschema abhängig ist; `_wctomb_l` ist mit `wctomb` identisch, nur dass sie stattdessen das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 `wctomb` überprüft die eigenen Parameter. Wenn `mbchar` `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt –&1; zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`wctomb`|\<stdlib.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Dieses Programm stellt das Verhalten der Funktion „wctomb“ dar.  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
