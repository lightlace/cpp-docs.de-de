---
title: _strdate, _wstrdate | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdate
- _wstrdate
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tstrdate
- wstrdate
- _wstrdate
- _strdate
- strdate
dev_langs: C++
helpviewer_keywords:
- strdate function
- dates, copying
- tstrdate function
- _wstrdate function
- wstrdate function
- _strdate function
- _tstrdate function
- copying dates
ms.assetid: de8e4097-58f8-42ba-9dcd-cb4d9a9f1696
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54c7aa7fda123e811f23c2cc4b9e8d81f76966df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strdate-wstrdate"></a>_strdate, _wstrdate
Kopieren des aktuellen Systemdatums in einen Puffer Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_strdate_s, _wstrdate_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_strdate(  
   char *datestr   
);  
wchar_t *_wstrdate(  
   wchar_t *datestr   
);  
template <size_t size>  
char *_strdate(  
   char (&datestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrdate(  
   wchar_t (&datestr)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `datestr`  
 Ein Zeiger auf einen Puffer, der die formatierte Datumszeichenfolge enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf die resultierende Zeichenfolge `datestr` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_strdate_s, _wstrdate_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md). Es wird empfohlen, nach Möglichkeit die sichereren Funktionen zu verwenden.  
  
 Die Funktion `_strdate` kopiert das aktuelle Datum in den Puffer, auf den `datestr` zeigt, im Format `mm`/`dd`/`yy`, wobei `mm` zwei Ziffern für den Monat, `dd` zwei Ziffern für den Tag und `yy` die letzten beiden Ziffern des Jahres darstellen. Beispiel: Die Zeichenfolge `12/05/99` stellt das Datum 5. Dezember 1999 dar. Der Puffer muss mindestens 9 Bytes lang sein.  
  
 Wenn `datestr` ein `NULL`-Zeiger ist, wird der Handler für ungültige Parameter, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL`fest.  
  
 `_wstrdate` ist eine Breitzeichenversion von `_strdate`. Das Argument und der Rückgabewert von `_wstrdate` sind Zeichenfolgen mit Breitzeichen. Anderenfalls verhalten sich diese Funktionen identisch.  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrdate`|`_strdate`|`_strdate`|`_wstrdate`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_strdate`|\<time.h>|  
|`_wstrdate`|\<time.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// strdate.c  
// compile with: /W3  
#include <time.h>  
#include <stdio.h>  
int main()  
{  
    char tmpbuf[9];  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    printf( "OS date: %s\n", _strdate(tmpbuf) ); // C4996  
    // Note: _strdate is deprecated; consider using _strdate_s instead  
}  
```  
  
```Output  
OS date: 04/25/03  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)