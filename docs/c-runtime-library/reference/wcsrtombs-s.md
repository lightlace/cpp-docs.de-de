---
title: wcsrtombs_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcsrtombs_s
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
f1_keywords: wcsrtombs_s
dev_langs: C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f8045010875713588fb20a8f05a230717a21a9a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="wcsrtombss"></a>wcsrtombs_s
Konvertieren von Breitzeichen in die Multibyte-Zeichenfolgendarstellung. Eine Version von [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) mit Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pReturnValue`  
 Die Anzahl von konvertierten Zeichen.  
  
 [out] `mbstr`  
 Die Pufferadresse für die resultierende konvertierte Multibyte-Zeichenfolge.  
  
 [out] `sizeInBytes`  
 Die Größe des `mbstr`-Puffers in Bytes.  
  
 [in] `wcstr`  
 Zeigt auf die zu konvertierende Breitzeichenfolge.  
  
 [in] `count`  
 Die maximale Anzahl der Bytes, die im `mbstr`-Puffer gespeichert werden sollen, oder [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in] `mbstate`  
 Ein Zeiger auf ein `mbstate_t`-Konvertierungszustandsobjekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
|Fehlerbedingung|Rückgabewert und `errno`|  
|---------------------|------------------------------|  
|`mbstr` ist gleich `NULL` und `sizeInBytes` > 0|`EINVAL`|  
|`wcstr` ist gleich `NULL`.|`EINVAL`|  
|Der Zielpuffer ist für die konvertierte Zeichenfolge zu klein (es sei denn, `count` ist gleich `_TRUNCATE`; siehe Abschnitt „Hinweise“)|`ERANGE`|  
  
 Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die Ausführung fortgesetzt werden kann, gibt die Funktion einen Fehlercode zurück und legt `errno` wie in der Tabelle angegeben fest.  
  
## <a name="remarks"></a>Hinweise  
 Die `wcsrtombs_s`-Funktion konvertiert eine Zeichenfolge mit Breitzeichen, auf die indirekt von `wcstr` gezeigt wird, in im Puffer gespeicherte Multibytezeichen, auf die von `mbstr` gezeigt wird, und verwendet dafür den in `mbstate` enthaltenen Konvertierungsstatus. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine der folgenden Bedingungen eintritt:  
  
-   Ein Breitzeichen NULL wird erkannt.  
  
-   Ein Breitzeichen, das nicht konvertiert werden kann, wird erkannt.  
  
-   Die Anzahl der Bytes, die im `mbstr`-Puffer gespeichert sind, ist gleich `count`.  
  
 Die Zielzeichenfolge endet immer mit NULL, selbst bei einem Fehler.  
  
 Wenn `count` der spezielle Wert [_TRUNCATE](../../c-runtime-library/truncate.md) ist, konvertiert `wcsrtombs_s` einen so großen Teil der Zeichenfolge wie in den Zielpuffer passt, während weiterhin Platz für ein NULL-Abschlusszeichen bleibt.  
  
 Wenn `wcsrtombs_s` die Quellzeichenfolge erfolgreich konvertiert, wird die Größe der konvertierten Zeichenfolge in Bytes und das NULL-Abschlusszeichen in `*pReturnValue` geschrieben, vorausgesetzt, `pReturnValue` ist ungleich `NULL`. Dieser Fehler tritt auch dann auf, wenn das `mbstr`-Argument `NULL` ist und es eine Methode zur Bestimmung der erforderlichen Puffergröße bietet. Bitte beachten Sie, dass `count` ignoriert wird, wenn `mbstr` gleich `NULL` ist.  
  
 Wenn `wcsrtombs_s` ein Breitzeichen erkennt, das nicht in ein Multibytezeichen konvertiert werden kann, wird -1 in `*pReturnValue` geschrieben, der Zielpuffer auf eine leere Zeichenfolge festgelegt, `errno` auf `EILSEQ` festgelegt und `EILSEQ` zurückgegeben.  
  
 Wenn die Sequenzen, auf die von `wcstr` und `mbstr` verwiesen wird, überlappen, ist das Verhalten von `wcsrtombs_s` nicht definiert. `wcsrtombs_s` wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `wcstr` und `mbstr` nicht überlappen und dass `count` die Anzahl zu konvertierender Breitzeichen korrekt darstellt.  
  
 Die Funktion `wcsrtombs_s` unterscheidet sich von [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md) durch die Neustartmöglichkeit. Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Beispiel: Eine Anwendung würde `wcsrlen` anstelle von `wcslen` verwenden, wenn ein nachfolgender Aufruf von `wcsrtombs_s` anstelle von `wcstombs_s.` verwendet würde.  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Ausnahmen  
 Die `wcsrtombs_s`-Funktion ist multithreadsicher, solange keine Funktion im aktuellen Thread `setlocale` aufruft, während diese Funktion ausgeführt wird und `mbstate` NULL ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfully converted.  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`wcsrtombs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)