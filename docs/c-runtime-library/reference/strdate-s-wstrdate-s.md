---
title: _strdate_s, _wstrdate_s
description: _strdate_s und _wstrdate_s sind sichere CRT-Versionen der _strdate-und _wstrdate-Funktionen, die das aktuelle Datum in einem Puffer platzieren.
ms.date: 11/01/2019
api_name:
- _strdate_s
- _wstrdate_s
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
ms.openlocfilehash: 7d04c134fcd19753ac0cecf8cc3b87e902d92e83
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625760"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Kopieren des aktuellen Systemdatums in einen Puffer. Diese Funktionen sind Versionen von [_strdate, _wstrdate](strdate-wstrdate.md) mit Sicherheitsverbesserungen, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md)beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t _strdate_s(
   char *buffer,
   size_t size
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t size
);
template <size_t size>
errno_t _strdate_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrdate_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>Parameter

*Puffer* \
Ein Zeiger auf einen Puffer, um die formatierte Datums Zeichenfolge zu platzieren.

*Größen* \
Größe des Puffers in Zeicheneinheiten.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in ERRNO.H definiert. Die genauen Fehler, die von der Funktion generiert werden, finden Sie in der folgenden Tabelle. Weitere Informationen zu Fehlercodes finden Sie unter [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Fehlerbedingungen

|*buffer*|*size*|Return|Inhalt des *Puffers*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(alle)|**EINVAL**|Nicht modifiziert|
|Not **null** (Verweis auf gültigen Puffer)|0|**EINVAL**|Nicht modifiziert|
|Not **null** (Verweis auf gültigen Puffer)|0 < *Größe* < 9|**EINVAL**|Leere Zeichenfolge|
|Not **null** (Verweis auf gültigen Puffer)|*Größe* > = 9|0|Aktuelles Datum, wie es in den Hinweisen angegeben wurde|

## <a name="security-issues"></a>Sicherheitsprobleme

Wenn Sie einen ungültigen Wert, der nicht NULL ist, für den *Puffer* übergeben, führt dies zu einer Zugriffsverletzung, wenn der *size* -Parameter größer als neun ist.

Wenn ein Wert für eine größere *Größe* als die tatsächliche *Puffer* Größe übergeben wird, führt dies zu einem Pufferüberlauf.

## <a name="remarks"></a>Hinweise

Diese Funktionen bieten sicherere Versionen von **_strdate** und **_wstrdate**. Die **_strdate_s** -Funktion kopiert das aktuelle Systemdatum in den Puffer, auf den von *buffer*verwiesen wird. Er ist `mm/dd/yy`formatiert, wobei `mm` der zweistellige Monat ist, `dd` der zweistellige Tag und `yy` die letzten zwei Ziffern des Jahres ist. Beispiel: Die Zeichenfolge `12/05/99` stellt das Datum 5. Dezember 1999 dar. Der Puffer muss mindestens neun Zeichen lang sein.

**_wstrdate_s** ist eine breit Zeichen Version von **_strdate_s**. Das Argument und der Rückgabewert von **_wstrdate_s** sind Zeichen folgen mit breit Zeichen. Anderenfalls verhalten sich diese Funktionen identisch.

Wenn *buffer* ein **null** -Zeiger ist oder die *Größe* weniger als neun Zeichen beträgt, wird der Handler für ungültige Parameter aufgerufen. Dies wird in [Parameter Validierung](../../c-runtime-library/parameter-validation.md)beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen-1 zurück. Sie legen **errno** auf **EINVAL** fest, wenn der Puffer **null** ist oder wenn die *Größe* kleiner oder gleich 0 ist. Oder Sie legen **errno** auf **ERANGE** fest, wenn die *Größe* kleiner als 9 ist.

In C++wird die Verwendung dieser Funktionen durch Vorlagen Überladungen vereinfacht. Die über Ladungen können automatisch die Pufferlänge ableiten, sodass kein *Größen* Argument angegeben werden muss. Außerdem können Sie automatisch nicht sichere Funktionen durch Ihre neueren, sichereren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).

Die Debug-Bibliotheksversionen dieser Funktionen füllen zunächst den Puffer mit "0xFE" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mapping"></a>Zuordnung von generischen Text Routinen:

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> oder \<wchar.h>|
|**_strdate_s**|\<time.h>|

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [time](time-time32-time64.md).

## <a name="see-also"></a>Siehe auch

[Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[time, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
