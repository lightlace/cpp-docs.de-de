---
title: _strdate_s, _wstrdate_s
ms.date: 11/04/2016
apiname:
- _strdate_s
- _wstrdate_s
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
ms.openlocfilehash: 85c9ab7dcad68f3aa4832236461cd38b07d4ae44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353988"
---
# <a name="strdates-wstrdates"></a>_strdate_s, _wstrdate_s

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

|*buffer*|*numberOfElements*|Zurück|Inhalt der *Puffer*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(alle)|**EINVAL**|Nicht geändert|
|Nicht **NULL** (zeigt auf gültigen Puffer)|0|**EINVAL**|Nicht geändert|
|Nicht **NULL** (zeigt auf gültigen Puffer)|0 < *NumberOfElements* < 9|**EINVAL**|Leere Zeichenfolge|
|Nicht **NULL** (zeigt auf gültigen Puffer)|*numberOfElements* >= 9|0|Aktuelles Datum, wie es in den Hinweisen angegeben wurde|

## <a name="security-issues"></a>Sicherheitsprobleme

Übergabe eines ungültigen nicht **NULL** Wert für der Puffer zu einer zugriffsverletzung führt, wenn die *NumberOfElements* Parameter größer als 9 ist.

Übergeben von Werten für die Größe, ist größer als die tatsächliche Größe der *Puffer* Pufferüberlauf führt.

## <a name="remarks"></a>Hinweise

Diese Funktionen bieten sicherere Versionen **_strdate** und **_wstrdate**. Die **_strdate_s** Funktion kopiert das aktuelle Datum in den Puffer, der auf *Puffer*, im Format **mm**/**TT** / **Yy**, wobei **mm** zwei Ziffern für den Monat **TT** zwei Ziffern für den Tag und **JJ**  ist die letzten zwei Ziffern des Jahres. Z. B. die Zeichenfolge **12/05/99** 5. Dezember 1999 darstellt. Die Zeichenfolge muss mindestens eine Länge von 9 Zeichen aufweisen.

**_wstrdate_s** ist eine Breitzeichen-Version von **_strdate_s**; der Wert Argument- und Rückgabetypen der **_wstrdate_s** sind Breitzeichen Zeichenfolgen. Anderenfalls verhalten sich diese Funktionen identisch.

Wenn *Puffer* ist eine **NULL** -Zeiger ist, oder wenn *NumberOfElements* ist kleiner als 9 Zeichen lang sein, den Handler für ungültige Parameter aufgerufen, siehe [ Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL** ist der Puffer **NULL** oder, wenn *NumberOfElements*ist kleiner als oder gleich 0, oder legen **Errno** zu **ERANGE** Wenn *NumberOfElements* weniger als 9 ist.

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
