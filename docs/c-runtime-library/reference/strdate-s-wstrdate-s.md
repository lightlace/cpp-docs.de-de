---
title: _strdate_s, _wstrdate_s
ms.date: 11/04/2016
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
ms.openlocfilehash: fadd30ec81cff59d675212e59c8513656c7b2f35
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940753"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s, _wstrdate_s

Kopieren des aktuellen Systemdatums in einen Puffer. Dies sind Versionen von [_strdate, _wstrdate](strdate-wstrdate.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t _strdate_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t numberOfElements
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

*buffer*<br/>
Ein Zeiger auf einen Puffer, der mit der formatierten Zeichenfolge ausgefüllt wird.

*numberOfElements*<br/>
Größe des Puffers.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in ERRNO.H definiert. Die genauen Fehler, die von der Funktion generiert werden, finden Sie in der folgenden Tabelle. Weitere Informationen zu Fehlercodes finden Sie unter [errno](../../c-runtime-library/errno-constants.md).

## <a name="error-conditions"></a>Fehlerbedingungen

|*buffer*|*numberOfElements*|Zurück|Inhalt des *Puffers*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(alle)|**EINVAL**|Nicht geändert|
|Not **null** (Verweis auf gültigen Puffer)|0|**EINVAL**|Nicht geändert|
|Not **null** (Verweis auf gültigen Puffer)|0 < der *Nummerierungen* < 9|**EINVAL**|Leere Zeichenfolge|
|Not **null** (Verweis auf gültigen Puffer)|*Nummerierungen* > = 9|0|Aktuelles Datum, wie es in den Hinweisen angegeben wurde|

## <a name="security-issues"></a>Sicherheitsprobleme

Wenn Sie einen ungültigen nicht- **null** -Wert für den Puffer übergeben, führt dies zu einer Zugriffsverletzung, wenn der Parameter " *numofelements* " größer als 9 ist.

Das übergeben von Werten für die Größe, die größer als die tatsächliche Größe des *Puffers* ist, führt zu einem Pufferüberlauf.

## <a name="remarks"></a>Hinweise

Diese Funktionen bieten sicherere Versionen von **_strdate** und **_wstrdate**. Die **_strdate_s** -Funktion kopiert das aktuelle Systemdatum in den Puffer, auf den vom *Puffer*, formatiert **mm**/**DD**/**yy**, verwiesen wird, wobei **mm** zwei Ziffern darstellt, die den Monat, dd, darstellen.gibt zwei Ziffern an, die den Tag darstellen, und **yy** ist die letzten zwei Ziffern des Jahres. Die Zeichenfolge **12/05/99** stellt z. b. den 5. Dezember 1999 dar. Die Zeichenfolge muss mindestens eine Länge von 9 Zeichen aufweisen.

**_wstrdate_s** ist eine breit Zeichen Version von **_strdate_s**. Das Argument und der Rückgabewert von **_wstrdate_s** sind Zeichen folgen mit breit Zeichen. Anderenfalls verhalten sich diese Funktionen identisch.

Wenn der *Puffer* ein **null** -Zeiger ist oder wenn " *suffiofelements* " weniger als 9 Zeichen umfasst, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "-1" zurück und setzen " **errno** " auf " **EINVAL** ", wenn der Puffer **null** ist, oder wenn " *numofelements* " kleiner oder gleich 0 ist, oder wenn " **errno** " auf " **ERANGE** " festgelegt istist kleiner als 9.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Zuordnung generischer Textroutinen:

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

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
