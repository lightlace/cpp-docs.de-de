---
title: wcrtomb_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcrtomb_s
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
f1_keywords: wcrtomb_s
dev_langs: C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13134a3e6b34be13d6d878cf94f204bb6c87a458
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wcrtombs"></a>wcrtomb_s
Konvertieren von Breitzeichen in die Multibyte-Zeichendarstellung. Eine Version von [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) mit Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pReturnValue`  
 Gibt die Anzahl geschriebener Bytes oder „-1“ bei einem Fehler zurück.  
  
 [out] `mbchar`  
 Das resultierende in Multibyte konvertierte Zeichen.  
  
 [in] `sizeOfmbchar`  
 Die Größe der Variablen `mbchar` in Bytes.  
  
 [in] `wchar`  
 Ein zu konvertierendes Breitzeichen.  
  
 [in] `mbstate`  
 Ein Zeiger auf ein `mbstate_t` -Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt null oder bei einem Fehler einen `errno`-Wert zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `wcrtomb_s` konvertiert ein Breitzeichen, beginnend beim angegebenen Konvertierungsstatus, der in `mbstate` enthalten ist, vom in `wchar` enthaltenen Wert in die von `mbchar` dargestellte Adresse. Der `pReturnValue`-Wert entspricht der Anzahl der konvertierten Bytes, jedoch nicht mehr als `MB_CUR_MAX` Bytes, oder -1 bei einem Fehler.  
  
 Wenn `mbstate` NULL ist, wird der interne Konvertierungsstatus `mbstate_t` verwendet. Wenn das in `wchar` enthaltene Zeichen nicht über ein entsprechendes Multibytezeichen verfügt, ist der Wert von `pReturnValue` -1, und die Funktion gibt den `errno`-Wert von `EILSEQ` zurück.  
  
 Die Funktion `wcrtomb_s` unterscheidet sich von [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) durch die Neustartmöglichkeit. Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Beispiel: Eine Anwendung würde `wcsrlen` anstelle von `wcslen` verwenden, wenn ein nachfolgender Aufruf von `wcsrtombs_s` anstelle von `wcstombs_s.` verwendet würde.  
  
 In C++ wird die Verwendung dieser Funktion durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Ausnahmen  
 Die `wcrtomb_s`-Funktion ist multithreadsicher, solange keine Funktion im aktuellen Thread `setlocale` aufruft, während diese Funktion ausgeführt wird und `mbstate` NULL ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
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
The corresponding wide character "Q" was converted to a the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`wcrtomb_s`|\<wchar.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)