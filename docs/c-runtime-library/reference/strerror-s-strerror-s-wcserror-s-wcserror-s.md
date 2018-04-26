---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce3ef36a621834f93402c6ec0a99a6ce7dedadda
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Abrufen eine Systemfehlermeldung (**Strerror_s**, **_wcserror_s**) oder Drucken einer vom Benutzer angegebenen Fehlermeldung (**_strerror_s**, **__wcserror_s** ). Dies sind Versionen von [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

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
|**NULL**|alle|alle|n/v|
|alle|0|alle|nicht geändert|

## <a name="remarks"></a>Hinweise

Die **Strerror_s** -Funktion ordnet *Errnum* Zurückgeben der an eine Zeichenfolge der Fehlermeldung, die Zeichenfolge in *Puffer*. **_strerror_s** braucht nicht die Fehlernummer, verwendet den aktuellen Wert der **Errno** auf die entsprechende Meldung zu bestimmen. Weder **Strerror_s** noch **_strerror_s** die Meldung gedruckt: dazu müssen Sie eine Ausgabefunktion wie z. B. [Fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

Wenn *StrErrMsg* ist **NULL**, **_strerror_s** gibt eine Zeichenfolge in *Puffer* , die die Systemfehlermeldung zu dem letzten Bibliotheksaufruf enthält. erzeugt einen Fehler. Die Fehlermeldungszeichenfolge wird durch das Zeilenumbruchzeichen ('\n') beendet. Wenn *StrErrMsg* stimmt nicht mit **NULL**, klicken Sie dann **_strerror_s** gibt eine Zeichenfolge in *Puffer* (in Reihenfolge) enthält, die zeichenfolgenmeldung, einen Doppelpunkt, ein Leerzeichen, die Systemfehlermeldung zu dem letzten Bibliotheksaufruf, erzeugt einen Fehler, und ein Zeilenumbruchzeichen. Die Zeichenfolgenmeldung darf höchstens 94 Zeichen lang sein.

Diese Funktionen schneiden die Fehlermeldung angezeigt, wenn seine Länge überschreitet *NumberOfElements* -1. Die resultierende Zeichenfolge in *Puffer* ist immer Null-terminierte.

Die tatsächliche Fehlernummer für **_strerror_s** ist in der Variablen gespeicherte [Errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Über die Variable [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird auf die Systemfehlermeldungen zugegriffen, die als Array von Meldungen nach Fehlernummern geordnet sind. **_strerror_s** greift auf die entsprechende Fehlermeldung mithilfe der **Errno** Wert als Index für die Variable **_sys_errlist**. Der Wert der Variablen [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ist definiert als die maximale Anzahl von Elementen in der **_sys_errlist** Array. Um vollständige Ergebnisse zu erzeugen, rufen **_strerror_s** sofort, nachdem eine Bibliotheksroutine einen Fehler zurückgibt. Andernfalls nachfolgende Aufrufe von **Strerror_s** oder **_strerror_s** können überschreiben die **Errno** Wert.

**_wcserror_s** und **__wcserror_s** sind Breitzeichenversionen von **Strerror_s** und **_strerror_s**zugeordnet.

Diese Funktionen überprüfen ihre Parameter. Wenn Puffer ist **NULL** oder wenn der Parameter 0 ist, wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, der Funktionen zurück **EINVAL** und **Errno** auf **EINVAL**.

**_strerror_s**, **_wcserror_s**, und **__wcserror_s** sind nicht Teil der ANSI-Definition, sondern Microsoft-Erweiterungen für sie. Verwenden Sie nicht diese wo-Portabilität gewünscht wird. Verwenden Sie für ANSI-Kompatibilität **Strerror_s** stattdessen.

Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Betrachten Sie das Beispiel für [perror](perror-wperror.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
