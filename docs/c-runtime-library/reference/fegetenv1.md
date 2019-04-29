---
title: fegetenv
ms.date: 04/05/2018
apiname:
- fetegenv
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
- fegetenv
- fenv/fegetenv
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
ms.openlocfilehash: d3985e4dd2b3944bcdddb79605887def7ba15473
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334410"
---
# <a name="fegetenv"></a>fegetenv

Speichert die aktuelle Gleitkommaumgebung in das angegebene Objekt.

## <a name="syntax"></a>Syntax

```C
int fegetenv(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parameter

*penv*<br/>
Zeiger auf ein **Fenv_t** Objekt, das die Werte der aktuellen gleitkommaumgebung enthalten.

## <a name="return-value"></a>Rückgabewert

Gibt 0, wenn die gleitkommaumgebung erfolgreich in gespeicherten *Penv*. Andernfalls wird ein Wert ungleich null zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Fegetenv** Funktion speichert die aktuelle gleitkommaumgebung in das Objekt verweist *Penv*. Die Gleitkommaumgebung ist ein Satz von Statusflags und Steuermodi, die Gleitkommaberechnungen beeinflussen. Darunter fallen auch das Rundungsverhalten und die Statusflags für Gleitkommaausnahmen.  Wenn *Penv* verweist nicht auf ein gültiges **Fenv_t** -Objekt resultierende Verhalten nicht definiert ist.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
