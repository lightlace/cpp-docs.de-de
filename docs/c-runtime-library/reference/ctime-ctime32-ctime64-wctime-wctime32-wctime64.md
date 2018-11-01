---
title: ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
ms.date: 11/04/2016
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
ms.openlocfilehash: d1858a36c68a2ca5cedf70a1d74d5f250cbac8df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580819"
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64

Konvertieren Sie einen Zeitwert in eine Zeichenfolge, und passen Sie sie an die Zeitzoneneinstellungen an. Sicherere Versionen dieser Funktionen sind verfügbar. Sie finden sie unter [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).

## <a name="syntax"></a>Syntax

```C
char *ctime( const time_t *sourceTime );
char *_ctime32( const __time32_t *sourceTime );
char *_ctime64( const __time64_t *sourceTime );
wchar_t *_wctime( const time_t *sourceTime );
wchar_t *_wctime32( const __time32_t *sourceTime );
wchar_t *_wctime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parameter

*sourceTime*<br/>
Zeiger auf die gespeicherte Zeit konvertiert.

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Zeichenfolgenergebnis **NULL** wird zurückgegeben, wenn:

- *SourceTime* stellt ein Datum vor Mitternacht, 1. Januar 1970 UTC.

- Bei Verwendung von **_ctime32** oder **_wctime32** und *SourceTime* stellt ein Datum nach 23:59:59 am 18. Januar 2038, UTC dar.

- Bei Verwendung von **_ctime64** oder **_wctime64** und *SourceTime* stellt ein Datum nach 23:59:59, 31. Dezember 3000 UTC dar.

**CTime** ist eine Inlinefunktion, die ergibt **_ctime64** und **Time_t** entspricht **__time64_t**. Wenn Sie erzwingen, dass den Compiler interpretiert müssen **Time_t** als das alte 32-Bit **Time_t**, können Sie definieren **_USE_32BIT_TIME_T**. Dadurch wird **Ctime** ergibt **_ctime32**. Dies ist nicht zu empfehlen, weil bei Ihrer Anwendung nach dem 18. Januar 2038 ein Fehler auftreten kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.

## <a name="remarks"></a>Hinweise

Die **Ctime** -Funktion konvertiert einen Zeitwert, gespeichert als eine [Time_t](../../c-runtime-library/standard-types.md) Wert in eine Zeichenfolge. Die *SourceTime* Wert wird in der Regel von einem Aufruf abgerufen [Zeit](time-time32-time64.md), gibt die Anzahl der Sekunden seit Mitternacht vergangenen (00: 00:00), 1. Januar 1970, koordinierte Weltzeit (UTC). Der Rückgabewert der Zeichenfolge enthält genau 26 Zeichen und sieht so aus:

```Output
Wed Jan 02 02:03:55 1980\n\0
```

Eine 24-Stunden-Uhr wird verwendet. Alle Felder haben eine feste Breite. Das Zeichen für neue Zeile ('\n') und das Nullzeichen ('\0') nehmen die letzten beiden Stellen der Zeichenfolge ein.

Die konvertierte Zeichenfolge wird auch gemäß den lokalen Zeitzoneneinstellungen angepasst. Finden Sie unter den [Zeit](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md), und [Localtime](localtime-localtime32-localtime64.md) Funktionen für die Informationen zum Konfigurieren der lokalen Zeit und die [_tzset](tzset.md) für Funktion Details zur Definition der zeitzonenumgebung und globalen Variablen.

Ein Aufruf von **Ctime** ändert die einzelnen statisch zugewiesenen Puffer ein, die die **Gmtime** und **Localtime** Funktionen. Bei jedem Aufruf dieser Routinen wird das Ergebnis des vorherigen Aufrufs zerstört. **CTime** teilt einen statischen Puffer mit der **Asctime** Funktion. Daher einen Aufruf von **Ctime** zerstört das Ergebnis des vorherigen Aufrufs um **Asctime**, **Localtime**, oder **Gmtime**.

**_wctime** und **_wctime64** stellen die Breitzeichen-Version des **Ctime** und **_ctime64**; einen Zeiger auf die Breitzeichen-Zeichenfolge zurückgibt. Andernfalls **_ctime64**, **_wctime**, und **_wctime64** Verhalten sich genauso wie **Ctime**.

Diese Funktionen überprüfen ihre Parameter. Wenn *SourceTime* ein null-Zeiger ist oder wenn die *SourceTime* Wert negativ ist, rufen diese Funktionen den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktionen geben **NULL** und **Errno** zu **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime**|**ctime**|**ctime**|**_wctime**|
|**_tctime32**|**_ctime32**|**_ctime32**|**_wctime32**|
|**_tctime64**|**_ctime64**|**_ctime64**|**_wctime64**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**ctime**|\<time.h>|
|**_ctime32**|\<time.h>|
|**_ctime64**|\<time.h>|
|**_wctime**|\<time.h> oder \<wchar.h>|
|**_wctime32**|\<time.h> oder \<wchar.h>|
|**_wctime64**|\<time.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_ctime64.c
// compile with: /W3
/* This program gets the current
* time in _time64_t form, then uses ctime to
* display the time in string form.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   __time64_t ltime;

   _time64( &ltime );
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996
   // Note: _ctime64 is deprecated; consider using _ctime64_s
}
```

```Output
The time is Wed Feb 13 16:04:43 2002
```

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
