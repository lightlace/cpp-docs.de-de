---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 11/04/2016
api_name:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
ms.openlocfilehash: f8d461566f748ce5af3d4b2aab443b5966c27dd7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958154"
---
# <a name="strerror_s-_strerror_s-_wcserror_s-__wcserror_s"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Sie erhalten eine System Fehlermeldung (**strerror_s**, **_wcserror_s**) oder Drucken eine vom Benutzer bereitgestellte Fehlermeldung ( **_strerror_s**, **__wcserror_s**). Dies sind Versionen von [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t strerror_s(
   char *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t _strerror_s(
   char *buffer,
   size_t numberOfElements,
   const char *strErrMsg
);
errno_t _wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t __wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *strErrMsg
);
template <size_t size>
errno_t strerror_s(
   char (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t _strerror_s(
   char (&buffer)[size],
   const char *strErrMsg
); // C++ only
template <size_t size>
errno_t _wcserror_s(
   wchar_t (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t __wcserror_s(
   wchar_t (&buffer)[size],
   const wchar_t *strErrMsg
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Puffer für die Fehlerzeichenfolge.

*numberOfElements*<br/>
Puffergröße.

*errnum*<br/>
Fehlernummer.

*strErrMsg*<br/>
Vom Benutzer angegebene Meldung.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, Fehlercode bei Fehler.

### <a name="error-condtions"></a>Fehlerbedingungen

|*buffer*|*numberOfElements*|*strErrMsg*|Inhalt des *Puffers*|
|--------------|------------------------|-----------------|--------------------------|
|**NULL**|any|any|n/v|
|any|0|any|nicht geändert|

## <a name="remarks"></a>Hinweise

Die **strerror_s** -Funktion ordnet *errnum* einer Fehlermeldungs Zeichenfolge zu und gibt die Zeichenfolge im *Puffer*zurück. **_strerror_s** übernimmt nicht die Fehlernummer. Er verwendet den aktuellen Wert von **errno** , um die entsprechende Meldung zu bestimmen. Weder **strerror_s** noch **_strerror_s** druckt tatsächlich die Meldung: Dazu muss eine Ausgabefunktion wie z. [b. fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)aufgerufen werden:

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

Wenn " *strauerrmsg* " den Wert **null**hat, gibt **_strerror_s** eine Zeichenfolge im *Puffer* zurück, die die System Fehlermeldung für den letzten Bibliotheks Rückruf enthält, der einen Fehler verursacht hat. Die Fehlermeldungszeichenfolge wird durch das Zeilenumbruchzeichen ('\n') beendet. Wenn " *Strauch* Meldung" nicht gleich **null**ist, gibt **_strerror_s** eine Zeichenfolge im *Puffer* zurück, die (in der angegebenen Reihenfolge) ihre Zeichen folgen Meldung, einen Doppelpunkt, ein Leerzeichen, die System Fehlermeldung für den letzten Bibliotheks Aufrufe, der einen Fehler erzeugt, und einen Zeilen Vorstrich enthält. Art. Die Zeichenfolgenmeldung darf höchstens 94 Zeichen lang sein.

Diese Funktionen schneiden die Fehlermeldung ab, wenn die Länge von " *numofelements* -1" überschritten wird. Die resultierende Zeichenfolge im *Puffer* wird immer mit Null beendet.

Die tatsächliche Fehlernummer für **_strerror_s** wird in der Variablen [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)gespeichert. Über die Variable [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird auf die Systemfehlermeldungen zugegriffen, die als Array von Meldungen nach Fehlernummern geordnet sind. **_strerror_s** greift auf die entsprechende Fehlermeldung zu, indem der **errno** -Wert als Index zur Variablen **_sys_errlist**verwendet wird. Der Wert der Variablen [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird als maximale Anzahl von Elementen im **_sys_errlist** -Array definiert. Um genaue Ergebnisse zu erzielen, rufen Sie **_strerror_s** sofort auf, nachdem eine Bibliotheks Routine mit einem Fehler zurückgegeben wurde. Andernfalls können nachfolgende Aufrufe von **strerror_s** oder **_strerror_s** den **errno** -Wert überschreiben.

**_wcserror_s** und **__wcserror_s** sind breit Zeichen Versionen von **strerror_s** bzw. **_strerror_s**.

Diese Funktionen überprüfen ihre Parameter. Wenn der Puffer **null** ist oder der Size-Parameter den Wert 0 hat, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md) Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben die Funktionen **EINVAL** zurück und legen **errno** auf **EINVAL**fest.

**_strerror_s**, **_wcserror_s**und **__wcserror_s** sind nicht Teil der ANSI-Definition, sondern sind stattdessen Microsoft-Erweiterungen. Verwenden Sie diese nicht, wenn Portabilität gewünscht ist. Verwenden Sie für ANSI-Kompatibilität stattdessen **strerror_s** .

Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Betrachten Sie das Beispiel für [perror](perror-wperror.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
