---
title: Timespec_get, _timespec32_get, _timespec64_get1
ms.date: 11/04/2016
apiname:
- timespec_get
- _timespec32_get
- _timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
ms.openlocfilehash: c1d0cbaf194060d816e31d397a9319ef47f75371
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638450"
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get, _timespec32_get, _timespec64_get

Legt das Intervall, auf das das erste Argument verweist, auf die aktuelle Kalenderzeit fest, basierend auf der angegebenen Zeitbasis.

## <a name="syntax"></a>Syntax

```C
int timespec_get(
    struct timespec* const time_spec,
    int const base
);
int _timespec32_get(
    struct _timespec32* const time_spec,
    int const base
);
int _timespec64_get(
    struct _timespec64* const time_spec,
    int const base
);

```

### <a name="parameters"></a>Parameter

*time_spec*<br/>
Zeiger auf eine Struktur, die auf die seit dem Beginn der Epoche verstrichene Zeit in Sekunden und Nanosekunden festgelegt ist.

*base*<br/>
Ein implementierungsspezifischer Wert ungleich null, der die Zeitbasis angibt.

## <a name="return-value"></a>Rückgabewert

Der Wert des *Basis* erfolgreich ist, andernfalls 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Timespec_get** Funktionen legen die aktuelle Uhrzeit in der Struktur verweist die *Time_spec* Argument. Alle Versionen dieser Struktur besitzen zwei Member, **Tv_sec** und **Tv_nsec**. Die **Tv_sec** Wert wird festgelegt, auf die ganze Zahl von Sekunden und **Tv_nsec** auf ganzzahlige Nanosekunden, gerundet auf die Auflösung der Systemuhr an, seit dem Beginn der Epoche, der anhand des *Basis*.

**Microsoft-spezifisch**

Diese Funktionen unterstützen nur **TIME_UTC** als die *Basis* Wert. Hiermit wird die *Time_spec* Wert, der die Anzahl der Sekunden und Nanosekunden seit dem Beginn der Epoche, Mitternacht, 1. Januar 1970, koordinierte Weltzeit (UTC). In einem **Struktur** **_timespec32**, **Tv_sec** ist eine **__time32_t** Wert. In einem **Struktur** **_timespec64**, **Tv_sec** ist eine **__time64_t** Wert. In einem **Struktur** **Timespec**, **Tv_sec** ist eine **Time_t** Typ, der 32-Bit oder 64 Bit lang, je nachdem, ob der Präprozessor Makro _USE_32BIT_TIME_T definiert ist. Die **Timespec_get** -Funktion ist eine Inlinefunktion, die aufruft **_timespec32_get** Wenn _USE_32BIT_TIME_T definiert ist; andernfalls ruft sie **_timespec64_get**.

**Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**Timespec_get**, **_timespec32_get**, **_timespec64_get**|C: \<time.h>, C++: \<ctime> oder \<time.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
