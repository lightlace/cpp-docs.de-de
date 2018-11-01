---
title: feholdexcept
ms.date: 04/05/2018
apiname:
- feholdexcept
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
- feholdexcept
- fenv/feholdexcept
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
ms.openlocfilehash: 26097398b9f9d498ab4c56690dc9c6cbb950bafb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525736"
---
# <a name="feholdexcept"></a>feholdexcept

Speichert die aktuelle Gleitkommaumgebung im angegebenen Objekt, löscht die Gleitkomma-Statusflags und setzt die Gleitkommaumgebung wenn möglich in den ununterbrochenen Modus.

## <a name="syntax"></a>Syntax

```C
int feholdexcept(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parameter

*penv*<br/>
Zeiger auf ein **Fenv_t** Objekt, das eine Kopie der gleitkommaumgebung enthalten.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn die Funktion erfolgreich Behandlung von nicht-Gleitkommaausnahmen aktivieren kann.

## <a name="remarks"></a>Hinweise

Die **Feholdexcept** Funktion dient zum Speichern des Zustands des die aktuelle gleitkommaumgebung in das **Fenv_t** Objekt verweist *Penv*, und die Umgebung festgelegt werden soll Unterbrechen Sie die Ausführung von Gleitkommaausnahmen nicht. Dies wird als ununterbrochener Modus bezeichnet.  Dieser Modus wird fortgesetzt, bis die Umgebung mithilfe von [fesetenv](fesetenv1.md) oder [feupdateenv](feupdateenv.md) wiederhergestellt wird.

Sie können diese Funktion am Anfang einer Unterroutine verwenden, die eine oder mehrere Gleitkommaausnahmen vor dem Aufrufer verbergen muss. Wenn eine Ausnahme melden möchten, löschen Sie einfach die unerwünschten Ausnahmen mithilfe von [Feclearexcept](feclearexcept1.md) und beenden Sie dann den ununterbrochenen Modus durch einen Aufruf von **Feupdateenv**.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
