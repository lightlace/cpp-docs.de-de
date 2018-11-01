---
title: fesetenv
ms.date: 04/05/2018
apiname:
- fesetenv
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
- fesetenv
- fenv/fesetenv
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 8c91bfbb89df964fed0a632d5fb5ebac47ebe948
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436147"
---
# <a name="fesetenv"></a>fesetenv

Legt die aktuelle Gleitkommaausnahme fest

## <a name="syntax"></a>Syntax

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>Parameter

*penv*<br/>
Zeiger auf eine **Fenv_t** Objekt, das eine gleitkommaumgebung als Satz von einem Aufruf von enthält [Fegetenv](fegetenv1.md) oder [Feholdexcept](feholdexcept2.md). Sie können die standardmäßigen Start Gleitkomma-Umgebung auch angeben, indem die **FE_DFL_ENV** Makro.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn die Umgebung erfolgreich eingerichtet wurde. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Fesetenv** -Funktion legt fest, die aktuelle gleitkommaumgebung aus dem Wert gespeichert, der **Fenv_t** Objekt verweist *Penv*. Die Gleitkommaumgebung ist ein Satz von Statusflags und Steuermodi, die Gleitkommaberechnungen beeinflussen. Dies beinhaltet das Rundungsverhalten und die Statusflags für Gleitkommaausnahmen.  Wenn *Penv* nicht **FE_DFL_ENV** oder verweist nicht auf ein gültiges **Fenv_t** -Objekt resultierende Verhalten nicht definiert ist.

Ein Aufruf dieser Funktion legt die Ausnahme Gleitkommaausnahme-Flags, die in der *Penv* -Objekt, aber es löst keine Ausnahmen.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
