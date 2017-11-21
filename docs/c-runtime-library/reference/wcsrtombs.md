---
title: wcsrtombs | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcsrtombs
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
f1_keywords: wcsrtombs
dev_langs: C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 71924eb149097c90fbfe2f3ceb2981ea45e97995
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="wcsrtombs"></a>wcsrtombs
Konvertieren von Breitzeichen in die Multibyte-Zeichenfolgendarstellung. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [wcsrtombs_s](../../c-runtime-library/reference/wcsrtombs-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `mbstr`  
 Der Adressspeicherort der resultierenden konvertierten Multibyte-Zeichenfolge.  
  
 [in] `wcstr`  
 Indirekter Zeiger auf den Speicherort der Breitzeichenfolge, die konvertiert werden soll.  
  
 [in] `count`  
 Die Anzahl der zu konvertierenden Zeichen.  
  
 [in] `mbstate`  
 Ein Zeiger auf ein `mbstate_t`-Konvertierungszustandsobjekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der erfolgreich konvertierten Bytes zurück, wobei das abschließende NULL-Byte (falls vorhanden) nicht eingeschlossen ist. Andernfalls wird bei einem Fehler -1 zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `wcsrtombs` konvertiert eine Zeichenfolge aus Breitzeichen, beginnend beim angegebenen Konvertierungsstatus, der in `mbstate` enthalten ist, von den Werten, auf die in `wcstr` indirekt gezeigt wird, in die Adresse von `mbstr`. Die Konvertierung wird für jedes Zeichen fortgeführt, bis ein abschließendes NULL-Breitzeichen gefunden wird, ein nicht übereinstimmendes Zeichen gefunden wird oder das nächste Zeichen den in `count` enthaltenen Grenzwert übersteigen würde. Wenn `wcsrtombs` das Breitzeichen NULL (L'\0') erkennt, entweder vor oder bei `count`, wird es in ein 8-Bit-0-Zeichen konvertiert und beendet.  
  
 Folglich endet die Multibyte-Zeichenfolge bei `mbstr` nur dann auf NULL, wenn `wcsrtombs` während der Konvertierung ein Breitzeichen NULL findet. Wenn die Sequenzen, auf die von `wcstr` und `mbstr` verwiesen wird, überlappen, ist das Verhalten von `wcsrtombs` nicht definiert. `wcsrtombs` wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.  
  
 Die Funktion `wcsrtombs` unterscheidet sich von [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) durch die Neustartmöglichkeit. Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Beispiel: Eine Anwendung würde `wcsrlen` anstelle von `wcsnlen` verwenden, wenn ein nachfolgender Aufruf von `wcsrtombs` anstelle von `wcstombs` verwendet würde.  
  
 Wenn das `mbstr`-Argument `NULL` ist, gibt `wcsrtombs` die erforderliche Größe der Zielzeichenfolge in Bytes zurück. Wenn `mbstate` NULL ist, wird der interne Konvertierungsstatus `mbstate_t` verwendet. Wenn die Zeichensequenz `wchar` nicht über eine entsprechende Multibyte-Zeichendarstellung verfügt, wird -1 zurückgegeben, und `errno` wird auf `EILSEQ` festgelegt.  
  
 In C++ hat diese Funktion eine Vorlagenüberladung, mit der die neuere, sichere Entsprechung dieser Funktion aufgerufen wird. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Ausnahmen  
 Die `wcsrtombs`-Funktion ist multithreadsicher, solange keine Funktion im aktuellen Thread `setlocale` aufruft, während diese Funktion ausgeführt wird und `mbstate` nicht NULL ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfuly converted.  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`wcsrtombs`|\<wchar.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)