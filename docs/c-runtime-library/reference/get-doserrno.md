---
title: _get_doserrno | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_doserrno
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
- _get_doserrno
- get_doserrno
dev_langs:
- C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7cef2c068fad2f18cb1d11d33e551588800cb64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399568"
---
# <a name="getdoserrno"></a>_get_doserrno

Ruft den Fehlerwert durch das Betriebssystem zurückgegeben werden, bevor es in übersetzt ein **Errno** Wert.

## <a name="syntax"></a>Syntax

```C
errno_t _get_doserrno( 
   int * pValue 
);
```

### <a name="parameters"></a>Parameter

*pValue*<br/>
Ein Zeiger auf eine ganze Zahl, die mit den aktuellen Wert der gefüllt werden die **_doserrno** globales Makro.

## <a name="return-value"></a>Rückgabewert

Wenn **_get_doserrno** erfolgreich ist, wird NULL zurückgegeben, falls dies fehlschlägt, wird ein Fehlercode zurückgegeben. Wenn *pValue* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_doserrno** globales Makro während der CRT-Initialisierung auf NULL festgelegt ist, bevor die prozessausführung beginnt. Es wird auf einen Betriebssystemfehlerwert gesetzt, der von jeder Funktion auf Systemebene zurückgegeben wird, die einen Betriebssystemfehler zurückgibt, und wird während der Ausführung niemals auf Null gesetzt. Beim Schreiben von Code zum Überprüfen der Fehlerwert zurückgegeben, von einer Funktion, die immer klar **_doserrno** mit [_set_doserrno](set-doserrno.md) vor dem Funktionsaufruf. Da eine andere Funktion überschreiben könnte **_doserrno**, überprüfen Sie den Wert mit **_get_doserrno** sofort nach dem Funktionsaufruf.

Wir empfehlen [_get_errno](get-errno.md) anstelle von **_get_doserrno** für portable Fehlercodes.

Mögliche Werte für **_doserrno** im definiert \<errno.h >.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h >, \<cerrno > (C++)|

**_get_doserrno** ist eine Microsoft-Erweiterung. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
