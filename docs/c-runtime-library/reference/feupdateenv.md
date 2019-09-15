---
title: feupdateenv
ms.date: 04/05/2018
api_name:
- feupdateenv
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
api_type:
- HeaderDef
f1_keywords:
- feupdateenv
- fenv/feupdateenv
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
ms.openlocfilehash: 8f40cab42e4a89b1fc5a100587b11b0e2aeeb55c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940985"
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

*nach-oben*<br/>
Zeiger auf ein **fenv_t** -Objekt, das eine Gleit Komma Umgebung enthält, wie durch einen Aufrufen von [fegetenv](fegetenv1.md) oder [feholdexcept](feholdexcept2.md)festgelegt. Sie können auch die standardmäßige Startgleitkommaumgebung mit dem Makro FE_DFL_ENV angeben.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn alle Aktionen erfolgreich abgeschlossen wurden. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die Funktion " **feupdateenv** " führt mehrere Aktionen aus. Zunächst speichert sie die aktuellen, ausgelösten Statusflags der Gleitkommaausnahmen in einem automatischen Speicher. Anschließend wird die aktuelle Gleit Komma Umgebung von dem Wert festgelegt, der im **fenv_t** -Objekt gespeichert ist, auf das von " *KV*" gezeigt wird. Wenn " *KV* " nicht **FE_DFL_ENV** ist oder nicht auf ein gültiges **fenv_t** -Objekt verweist, ist das nachfolgende Verhalten nicht definiert. Zum Schluss löst **feupdateerv** die lokal gespeicherten Gleit Komma Ausnahmen aus.

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
