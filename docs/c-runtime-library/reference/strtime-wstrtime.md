---
title: _strtime, _wstrtime
ms.date: 11/04/2016
apiname:
- _wstrtime
- _strtime
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
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
ms.openlocfilehash: 9d874321418854a703886eb80ee23ac1cba57fa4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431120"
---
# <a name="strtime-wstrtime"></a>_strtime, _wstrtime

Kopieren der Zeit in einen Puffer. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md).

## <a name="syntax"></a>Syntax

```C
char *_strtime(
   char *timestr
);
wchar_t *_wstrtime(
   wchar_t *timestr
);
template <size_t size>
char *_strtime(
   char (&timestr)[size]
); // C++ only
template <size_t size>
wchar_t *_wstrtime(
   wchar_t (&timestr)[size]
); // C++ only
```

### <a name="parameters"></a>Parameter

*timestr*<br/>
Zeitzeichenfolge

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die resultierende Zeichenfolge *Timestr*.

## <a name="remarks"></a>Hinweise

Die **_strtime** Funktion kopiert die aktuelle lokale Zeit in den Puffer, der auf *Timestr*. Die Zeit wird als formatiert **hh: mm:** , in denen **Hh** zwei Ziffern für die Stunde im 24-Stunden-Notation **mm** zwei Ziffern für die Minuten nach der Stunde und **ss** zwei Ziffern für Sekunden. Z. B. die Zeichenfolge **18:23:44** stellt 23 Minuten und 44 Sekunden nach 6 Uhr Der Puffer muss mindestens 9 Bytes lang sein.

**_wstrtime** ist eine Breitzeichen-Version von **_strtime**; der Wert Argument- und Rückgabetypen der **_wstrtime** sind Breitzeichen Zeichenfolgen. Anderenfalls verhalten sich diese Funktionen identisch. Wenn *Timestr* ist eine **NULL** Zeiger oder wenn *Timestr* falsch formatiert ist, die ungültige parameterhandler wird aufgerufen, wie in beschrieben [Parameter Überprüfung](../../c-runtime-library/parameter-validation.md). Wenn die Ausnahme zulässig ist, um den Vorgang fortzusetzen, geben diese Funktionen zurück eine **NULL** und **Errno** zu **EINVAL** Wenn *Timestr* wurde eine **NULL** oder **Errno** zu **ERANGE** Wenn *Timestr* ist falsch formatiert.

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_strtime**|\<time.h>|
|**_wstrtime**|\<time.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_strtime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
   char tbuffer [9];
   _strtime( tbuffer ); // C4996
   // Note: _strtime is deprecated; consider using _strtime_s instead
   printf( "The current time is %s \n", tbuffer );
}
```

```Output
The current time is 14:21:44
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
