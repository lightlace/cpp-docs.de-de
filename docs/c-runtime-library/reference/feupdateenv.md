---
title: feupdateenv
ms.date: 04/05/2018
apiname:
- feupdateenv
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
apitype: HeaderDef
f1_keywords:
- feupdateenv
- fenv/feupdateenv
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
ms.openlocfilehash: 6d553d6899f55f5bdfb3ff313e88abfcb56ab4ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605109"
---
# <a name="feupdateenv"></a>feupdateenv

Speichert die aktuell ausgelösten Gleitkommaausnahmen, stellt den Zustand der angegebenen Gleitkommaumgebung wieder her und löst dann die gespeicherten Gleitkommaausnahmen aus.

## <a name="syntax"></a>Syntax

```C
int feupdateenv(
   const fenv_t* penv
);
```

### <a name="parameters"></a>Parameter

*penv*<br/>
Zeiger auf eine **Fenv_t** Objekt, das eine gleitkommaumgebung als Satz von einem Aufruf von enthält [Fegetenv](fegetenv1.md) oder [Feholdexcept](feholdexcept2.md). Sie können auch die standardmäßige Startgleitkommaumgebung mit dem Makro FE_DFL_ENV angeben.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn alle Aktionen erfolgreich abgeschlossen wurden. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Feupdateenv** Funktion führt mehrere Aktionen. Zunächst speichert sie die aktuellen, ausgelösten Statusflags der Gleitkommaausnahmen in einem automatischen Speicher. Klicken Sie dann die aktuelle gleitkommaumgebung aus dem Wert, der in gespeicherten wird die **Fenv_t** Objekt verweist *Penv*. Wenn *Penv* nicht **FE_DFL_ENV** oder verweist nicht auf ein gültiges **Fenv_t** -Objekt resultierende Verhalten nicht definiert ist. Zum Schluss **Feupdateenv** löst die lokal gespeicherten Gleitkommaausnahmen.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
