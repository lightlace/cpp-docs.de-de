---
title: wcrtomb | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- wcrtomb
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
- wcrtomb
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 203b3ec1d72b7691aa8e46d60784100c0bf89a5e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="wcrtomb"></a>wcrtomb
Konvertieren von Breitzeichen in die Multibyte-Zeichendarstellung. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `mbchar`  
 Das resultierende in Multibyte konvertierte Zeichen.  
  
 [in] `wchar`  
 Ein zu konvertierendes Breitzeichen.  
  
 [in] `mbstate`  
 Ein Zeiger auf ein `mbstate_t` -Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Bytes zurück, die erforderlich sind, um das konvertierte Multibytezeichen darzustellen, oder andernfalls -1, wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `wcrtomb` konvertiert ein Breitzeichen, beginnend beim angegebenen Konvertierungsstatus, der in `mbstate` enthalten ist, vom in `wchar` enthaltenen Wert in die von `mbchar` dargestellte Adresse. Der Rückgabewert ist die Anzahl der Bytes, die erforderlich sind, um das entsprechende Multibytezeichen darzustellen. Es werden jedoch höchstens `MB_CUR_MAX` Bytes zurückgegeben.  
  
 Wenn `mbstate` NULL ist, wird das interne `mbstate_t`-Objekt verwendet, das den Konvertierungsstatus von `mbchar` enthält. Wenn die Zeichensequenz `wchar` nicht über eine entsprechende Multibyte-Zeichendarstellung verfügt, wird -1 zurückgegeben, und `errno` wird auf `EILSEQ` festgelegt.  
  
 Die `wcrtomb`-Funktion unterscheidet sich von [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) durch die Neustartmöglichkeit. Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Beispiel: Eine Anwendung würde `wcsrlen` anstelle von `wcsnlen` verwenden, wenn ein nachfolgender Aufruf von `wcsrtombs` anstelle von `wcstombs` verwendet würde.  
  
 In C++ hat diese Funktion eine Vorlagenüberladung, mit der die neuere, sichere Entsprechung dieser Funktion aufgerufen wird. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Ausnahmen  
 Die `wcrtomb`-Funktion ist multithreadsicher, solange keine Funktion im aktuellen Thread `setlocale` aufruft, während diese Funktion ausgeführt wird und `mbstate` NULL ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
The corresponding wide character "Q" was converted to the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`wcrtomb`|\<wchar.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)