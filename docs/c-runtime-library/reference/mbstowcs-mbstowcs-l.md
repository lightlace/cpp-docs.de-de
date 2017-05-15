---
title: mbstowcs, _mbstowcs_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbstowcs
- _mbstowcs_l
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
- mbstowcs
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_l function
- mbstowcs_l function
- mbstowcs function
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
caps.latest.revision: 30
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 436e581907e3b651716e819a9c82a24eed2e4b8e
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="mbstowcs-mbstowcsl"></a>mbstowcs, _mbstowcs_l
Konvertiert eine Multibyte-Zeichensequenz in eine entsprechende Breitzeichensequenz. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_mbsnbcpy_s, _mbsnbcpy_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t mbstowcs(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count   
);  
size_t _mbstowcs_l(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t mbstowcs(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _mbstowcs_l(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `wcstr`  
 Adresse einer Breitzeichensequenz.  
  
 [in] `mbstr`  
 Adresse einer Multibyte-Zeichensequenz.  
  
 [in] `count`  
 Die maximale Anzahl zu konvertierender Multibytezeichen.  
  
 [in] `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn `mbstowcs` die Quellzeichenfolge erfolgreich konvertiert, gibt es die Anzahl von konvertierten Multibytezeichen zurück. Wenn das `wcstr`-Argument `NULL` ist, gibt die Funktion die erforderliche Größe der Zielzeichenfolge (in Breitzeichen) zurück. Wenn `mbstowcs` findet ein ungültiges Multibytezeichen wird-1 zurückgegeben. Wenn der Rückgabewert `count` ist, endet die Breitzeichenfolge nicht mit NULL.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `wcstr` und `mbstr` nicht überlappen und dass `count` die Anzahl zu konvertierenderMultibytezeichen korrekt darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `mbstowcs`-Funktion konvertiert `count`-Multibytezeichen, bis zu einer maximalen Anzahl, auf die von `mbstr` verwiesen wird, in eine entsprechende Breitzeichenfolge, die vom aktuellen Gebietsschema angegeben werden. Er speichert die resultierende Breitzeichen-Zeichenfolge an der Adresse dargestellte `wcstr`. Das Ergebnis ähnelt dem einer Reihe von Aufrufen an `mbtowc`. Wenn `mbstowcs` das Singlebyte-Zeichen NULL ('\0') erkennt, entweder bevor oder nachdem `count` aufgetreten ist, konvertiert es das Zeichen NULL in ein Breitzeichen-Zeichen NULL(L'\0') und hält an. Folglich endet die Breitzeichen-Zeichenfolge bei `wcstr` nur dann auf NULL, wenn ein NULL-Zeichen während der Konvertierung erkannt wird. Wenn die Sequenzen, auf die von `wcstr` und `mbstr` verwiesen wird, überlappen, ist das Verhalten nicht definiert.  
  
 Wenn das `wcstr`-Argument `NULL` ist, gibt `mbstowcs` die Anzahl von Breitzeichen zurück, die bei einer Konvertierung entstehen würden; ein NULL-Terminator wird dabei nicht eingeschlossen. Die Quellzeichenfolge muss auf NULL enden, damit der korrekte Wert zurückgegeben wird. Wenn Sie wollen, dass die resultierende Breitzeichenfolge auf NULL endet, fügen Sie dem Rückgabewert 1 hinzu.  
  
 Wenn das `mbstr`-Argumente `NULL` ist, oder wenn `count` >`INT_MAX` ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird errno auf `EINVAL` festgelegt, und die Funktion gibt –1 zurück.  
  
 `mbstowcs` verwendet das aktuelle Gebietsschema für jedes Verhalten, das vom Gebietsschema abhängig ist; `_mbstowcs_l` ist identisch, nur dass sie stattdessen das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`mbstowcs`|\<stdlib.h>|  
|`_mbstowcs_l`|\<stdlib.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_mbstowcs.c  
// compile with: /W3  
// illustrates the behavior of the mbstowcs function  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main( void )  
{  
    size_t size;  
    int nChar = 2; // number of characters to convert  
    int requiredSize;  
  
    unsigned char    *pmbnull  = NULL;  
    unsigned char    *pmbhello = NULL;  
    char* localeInfo;  
  
    wchar_t *pwchello = L"\x3042\x3043"; // 2 Hiragana characters  
    wchar_t *pwc;  
  
    /* Enable the Japanese locale and codepage */  
    localeInfo = setlocale(LC_ALL, "Japanese_Japan.932");  
    printf("Locale information set to %s\n", localeInfo);  
  
    printf( "Convert to multibyte string:\n" );  
  
    requiredSize = wcstombs( NULL, pwchello, 0); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    printf("  Required Size: %d\n", requiredSize);  
  
    /* Add one to leave room for the null terminator. */  
    pmbhello = (unsigned char *)malloc( requiredSize + 1);  
    if (! pmbhello)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = wcstombs( pmbhello, pwchello, requiredSize + 1); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    if (size == (size_t) (-1))  
    {  
        printf("Couldn't convert string. Code page 932 may"  
                " not be available.\n");  
        return 1;  
    }  
    printf( "  Number of bytes written to multibyte string: %u\n",  
            (unsigned int) size );  
    printf( "  Hex values of the " );  
    printf( " multibyte characters: %#.2x %#.2x %#.2x %#.2x\n",  
            pmbhello[0], pmbhello[1], pmbhello[2], pmbhello[3] );  
    printf( "  Codepage 932 uses 0x81 to 0x9f as lead bytes.\n\n");  
  
    printf( "Convert back to wide-character string:\n" );  
  
    /* Assume we don't know the length of the multibyte string.  
     Get the required size in characters, and allocate enough space. */  
  
    requiredSize = mbstowcs(NULL, pmbhello, 0); // C4996  
    /* Add one to leave room for the NULL terminator */  
    pwc = (wchar_t *)malloc( (requiredSize + 1) * sizeof( wchar_t ));  
    if (! pwc)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = mbstowcs( pwc, pmbhello, requiredSize + 1); // C4996  
    if (size == (size_t) (-1))  
    {  
       printf("Couldn't convert string--invalid multibyte character.\n");  
    }  
    printf( "  Characters converted: %u\n", (unsigned int)size );  
    printf( "  Hex value of first 2" );  
    printf( " wide characters: %#.4x %#.4x\n\n", pwc[0], pwc[1] );  
    free(pwc);  
    free(pmbhello);  
}  
```  
  
```Output  
Locale information set to Japanese_Japan.932  
Convert to multibyte string:  
  Required Size: 4  
  Number of bytes written to multibyte string: 4  
  Hex values of the  multibyte characters: 0x82 0xa0 0x82 0xa1  
  Codepage 932 uses 0x81 to 0x9f as lead bytes.  
  
Convert back to wide-character string:  
  Characters converted: 2  
  Hex value of first 2 wide characters: 0x3042 0x3043  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)
