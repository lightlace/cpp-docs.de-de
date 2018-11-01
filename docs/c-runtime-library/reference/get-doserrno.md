---
title: _get_doserrno
ms.date: 11/04/2016
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
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: d28b9ec47108f7051a908f874584bbfddf5d6a3d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605165"
---
# <a name="getdoserrno"></a>_get_doserrno

Ruft den Fehlerwert durch das Betriebssystem zurückgegeben werden, bevor es übersetzt ist ein **Errno** Wert.

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

Wenn **_get_doserrno** erfolgreich ist, wird 0 (null); schlägt fehl, es wird ein Fehlercode zurückgegeben. Wenn *pValue* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_doserrno** globalen Makros, die während der CRT-Initialisierung auf NULL festgelegt ist, bevor die prozessausführung beginnt. Es wird auf einen Betriebssystemfehlerwert gesetzt, der von jeder Funktion auf Systemebene zurückgegeben wird, die einen Betriebssystemfehler zurückgibt, und wird während der Ausführung niemals auf Null gesetzt. Beim Erstellen von Code zum Überprüfen der Wert des Fehlercodes von einer Funktion zurückgegebenen, immer löschen **_doserrno** mit [_set_doserrno](set-doserrno.md) vor dem Funktionsaufruf. Da eine andere Funktion überschreiben könnte **_doserrno**, überprüfen Sie den Wert mithilfe von **_get_doserrno** sofort nach dem Funktionsaufruf.

Es wird empfohlen [_get_errno](get-errno.md) anstelle von **_get_doserrno** für übertragbare Fehlercodes.

Mögliche Werte für **_doserrno** in definiert \<errno.h >.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h >, \<cerrno > (C++)|

**_get_doserrno** ist eine Microsoft-Erweiterung. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
