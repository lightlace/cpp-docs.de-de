---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 11/04/2016
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 00ff9d0df1a78d07eaa509201fb998b30396cc4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353819"
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Abrufen eine Systemfehlermeldung (**Strerror_s**, **_wcserror_s**) oder Drucken einer vom Benutzer bereitgestellten Fehlermeldung (**_strerror_s**, **__wcserror_s** ). Dies sind Versionen von [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

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

|*buffer*|*numberOfElements*|*strErrMsg*|Inhalt der *Puffer*|
|--------------|------------------------|-----------------|--------------------------|
|**NULL**|any|any|n/v|
|any|0|any|nicht geändert|

## <a name="remarks"></a>Hinweise

Die **Strerror_s** -Funktion ordnet *Errnum* auf eine Zeichenfolge der Fehlermeldung zurückgeben der Zeichenfolge in *Puffer*. **_strerror_s** braucht nicht die Fehlernummer, er verwendet den aktuellen Wert der **Errno** auf die entsprechende Meldung zu bestimmen. Weder **Strerror_s** noch **_strerror_s** tatsächlich wird die Meldung ausgegeben: Dazu müssen Sie zum Aufrufen einer Funktion wie [Fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

Wenn *StrErrMsg* ist **NULL**, **_strerror_s** gibt eine Zeichenfolge im *Puffer* , die die Systemfehlermeldung zu dem letzten Bibliotheksaufruf enthält. die einen Fehler produziert. Die Fehlermeldungszeichenfolge wird durch das Zeilenumbruchzeichen ('\n') beendet. Wenn *StrErrMsg* ist nicht gleich **NULL**, klicken Sie dann **_strerror_s** gibt eine Zeichenfolge im *Puffer* enthält (in Reihenfolge) die zeichenfolgenmeldung, einen Doppelpunkt ein Leerzeichen, die Systemfehlermeldung für den letzten Bibliotheksaufruf keinen Fehler, und ein Zeilenumbruchzeichen. Die Zeichenfolgenmeldung darf höchstens 94 Zeichen lang sein.

Diese Funktionen schneiden die Fehlermeldung angezeigt, wenn seine Länge überschreitet *NumberOfElements* -1. Die resultierende Zeichenfolge in *Puffer* ist immer Null-terminiert.

Die tatsächliche Fehlernummer für **_strerror_s** befindet sich in der Variablen [Errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Über die Variable [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird auf die Systemfehlermeldungen zugegriffen, die als Array von Meldungen nach Fehlernummern geordnet sind. **_strerror_s** greift auf die entsprechende Fehlermeldung an, indem die **Errno** Wert als Index für die Variable **_sys_errlist**. Der Wert der Variablen [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ist definiert als die maximale Anzahl von Elementen in der **_sys_errlist** Array. Um genaue Ergebnisse zu erzeugen, rufen Sie **_strerror_s** sofort, nachdem eine Bibliotheksroutine einen Fehler zurückgibt. Andernfalls, schlagen nachfolgende Aufrufe **Strerror_s** oder **_strerror_s** überschrieben werden kann die **Errno** Wert.

**_wcserror_s** und **__wcserror_s** sind Breitzeichenversionen von **Strerror_s** und **_strerror_s**bzw.

Diese Funktionen überprüfen ihre Parameter. Wenn der Puffer **NULL** oder der Größenparameter 0 ist, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktionen geben **EINVAL** und **Errno** zu **EINVAL**.

**_strerror_s**, **_wcserror_s**, und **__wcserror_s** sind nicht Teil der ANSI-Definition, sondern Microsoft-Erweiterungen für sie. Verwenden Sie sie nicht, in dem ist-Portabilität gewünscht; Verwenden Sie für ANSI-Kompatibilität **Strerror_s** stattdessen.

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
