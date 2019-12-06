---
title: feraiseexcept
ms.date: 04/05/2018
api_name:
- feraiseexcept
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
- feraiseexcept
- fenv/feraiseexcept
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
ms.openlocfilehash: 07c8a79e0a9569db80607e1ec1e16cd4b502783c
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857826"
---
# <a name="feraiseexcept"></a>feraiseexcept

Löst die angegebenen Gleitkommaausnahmen aus

## <a name="syntax"></a>Syntax

```C
int feraiseexcept(
   int excepts
);
```

### <a name="parameters"></a>Parameters

*ausgenommen*<br/>
Die auszulösenden Gleitkommaausnahmen

## <a name="return-value"></a>Rückgabewert

Wenn alle angegebenen Ausnahmen erfolgreich ausgelöst werden, wird 0 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **feraianwith** -Funktion versucht, die durch *Exception*angegebenen Gleit Komma Ausnahmen zu erhöhen.   Die **feraionaußer** -Funktion unterstützt diese Ausnahme Makros, die in \<fenv. h-> definiert sind:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALLEXCEPT|Bitweises OR oder alle unterstützten Gleitkommaausnahmen.|

Das *excepts* -Argument kann NULL, einer der ausnahmemakrowerte oder das bitweise OR von mindestens zwei unterstützten Ausnahme Makros sein. Wenn eines der angegebenen Ausnahmemakros FE_OVERFLOW oder FE_UNDERFLOW ist, kann die Ausnahme FE_INEXACT als Nebeneffekt ausgelöst werden.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

**Microsoft-spezifisch:** Die in " *excepts* " angegebenen Ausnahmen werden in der Reihenfolge FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT ausgelöst. FE_INEXACT können jedoch auch dann ausgelöst werden, wenn FE_OVERFLOW oder FE_UNDERFLOW ausgelöst wird, auch wenn Sie nicht in " *excepts*" angegeben sind.

## <a name="requirements"></a>-Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|*feraiseexcept*|\<fenv.h>|\<cfenv>|

Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
