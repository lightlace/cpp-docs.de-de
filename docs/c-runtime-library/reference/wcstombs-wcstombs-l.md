---
title: wcstombs, _wcstombs_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstombs
- _wcstombs_l
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
- wcstombs
- _wcstombs_l
dev_langs:
- C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: dead533ee11db7c40faa7d3611b30c6a6159ee50
ms.lasthandoff: 02/24/2017

---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l
Konvertiert eine Breitzeichensequenz in eine entsprechende Multibyte-Zeichensequenz. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `mbstr`  
 Die Adresse einer Multibyte-Zeichensequenz.  
  
 `wcstr`  
 Die Adresse einer Breitzeichensequenz.  
  
 `count`  
 Die maximale Anzahl von Bytes, die in der Multibyte-Ausgabezeichenfolge gespeichert werden können.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn `wcstombs` die Multibyte-Zeichenfolge erfolgreich konvertiert, wird die Anzahl der Bytes zurückgegeben, die in die Multibyte-Ausgabezeichenfolge geschrieben werden, mit Ausnahme des abschließenden Zeichens `NULL` (falls vorhanden). Wenn das `mbstr`-Argument `NULL` ist, gibt `wcstombs` die erforderliche Größe der Zielzeichenfolge in Bytes zurück. Wenn `wcstombs` ein Breitzeichen erkennt, das nicht in ein Multibytezeichen konvertiert werden kann, wird der in den Typ `size_t` umgewandelte Wert -1 zurückgegeben und `errno` auf `EILSEQ` festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `wcstombs` konvertiert die Breitzeichenfolge, auf die von `wcstr` gezeigt wird, in die entsprechenden Multibytezeichen und speichert die Ergebnisse im `mbstr`-Array. Der Parameter `count` zeigt die maximale Anzahl von Bytes an, die in der Multibyte-Ausgabezeichenfolge gespeichert werden können (d.h. die Größe von `mbstr`). Es ist allgemein nicht bekannt, wie viele Bytes bei der Konvertierung einer Breitzeichenfolge benötigt werden. Einige Breitzeichen benötigen nur ein Byte in der Ausgabezeichenfolge; andere erfordern zwei. Wenn für jedes Breitzeichen in der Eingabezeichenfolge (einschließlich des Breitzeichens `NULL`) zwei Bytes in der Multibyte-Ausgabezeichenfolge vorhanden sind, ist das Ergebnis garantiert passend.  
  
 Wenn `wcstombs` das Breitzeichen NULL (L'\0') erkennt, entweder vor oder bei `count`, wird es in ein 8-Bit-0-Zeichen konvertiert und beendet. Folglich endet die Multibyte-Zeichenfolge bei `mbstr` nur dann auf NULL, wenn `wcstombs` während der Konvertierung ein Breitzeichen NULL findet. Wenn die Sequenzen, auf die von `wcstr` und `mbstr` verwiesen wird, überlappen, ist das Verhalten von `wcstombs` nicht definiert.  
  
 Wenn das `mbstr`-Argument `NULL` ist, gibt `wcstombs` die erforderliche Größe der Zielzeichenfolge in Bytes zurück.  
  
 `wcstombs` überprüft die eigenen Parameter. Wenn `wcstr` gleich `NULL` oder `count` größer als `INT_MAX` ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt die Funktion `errno` auf `EINVAL` fest und gibt -1 zurück.  
  
 `wcstombs` verwendet das aktuelle Gebietsschema für jedes Verhalten, das vom Gebietsschema abhängig ist; `_wcstombs_l` ist identisch, nur dass sie stattdessen das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`wcstombs`|\<stdlib.h>|  
|`_wcstombs_l`|\<stdlib.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Dieses Programm stellt das Verhalten der Funktion `wcstombs` dar.  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 13  
    Multibyte character: Hello, world.  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
