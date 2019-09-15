---
title: _get_doserrno
ms.date: 11/04/2016
api_name:
- _get_doserrno
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
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 2810ead8bdd7d6c77cb2b55f4f97371bfc9751e6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956041"
---
# <a name="_get_doserrno"></a>_get_doserrno

Ruft den vom Betriebssystem zurückgegebenen Fehlerwert ab, bevor dieser in einen **errno** -Wert übersetzt wird.

## <a name="syntax"></a>Syntax

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>Parameter

*pValue*<br/>
Ein Zeiger auf eine Ganzzahl, die mit dem aktuellen Wert des globalen Makros **_doserrno** aufgefüllt werden soll.

## <a name="return-value"></a>Rückgabewert

Wenn **_get_doserrno** erfolgreich ist, wird NULL zurückgegeben. Wenn ein Fehler auftritt, wird ein Fehlercode zurückgegeben. Wenn *pValue* **null**ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion " **errno** " auf " **EINVAL** " fest und gibt " **EINVAL**" zurück.

## <a name="remarks"></a>Hinweise

Das globale Makro **_doserrno** wird während der CRT-Initialisierung auf NULL festgelegt, bevor die Prozess Ausführung beginnt. Es wird auf einen Betriebssystemfehlerwert gesetzt, der von jeder Funktion auf Systemebene zurückgegeben wird, die einen Betriebssystemfehler zurückgibt, und wird während der Ausführung niemals auf Null gesetzt. Wenn Sie Code zum Überprüfen des von einer Funktion zurückgegebenen Fehler Werts schreiben, löschen Sie **_doserrno** stets mit [_set_doserrno](set-doserrno.md) vor dem Funktions aufzurufen. Da ein anderer Funktions Aufrufwert **_doserrno**überschreiben kann, überprüfen Sie den Wert, indem Sie **_get_doserrno** unmittelbar nach dem Funktions aufzurufen.

Wir empfehlen [_get_errno](get-errno.md) anstelle von **_get_doserrno** für tragbare Fehlercodes.

Mögliche Werte von **_doserrno** werden in \<errno. h > definiert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h >, \<cerrno > (C++)|

**_get_doserrno** ist eine Microsoft-Erweiterung. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
