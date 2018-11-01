---
title: feraiseexcept
ms.date: 04/05/2018
apiname:
- feraiseexcept
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
- feraiseexcept
- fenv/feraiseexcept
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
ms.openlocfilehash: 581dd4026a20ce7221945c5815af3ae102f132fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532248"
---
# <a name="feraiseexcept"></a>feraiseexcept

Löst die angegebenen Gleitkommaausnahmen aus

## <a name="syntax"></a>Syntax

```C
int feraiseexcept(
   int excepts
);
```

### <a name="parameters"></a>Parameter

*Ausnahme*<br/>
Die auszulösenden Gleitkommaausnahmen

## <a name="return-value"></a>Rückgabewert

Wenn alle angegebenen Ausnahmen erfolgreich ausgelöst werden, wird 0 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Feraiseexcept** Funktion versucht, die vom angegebenen Gleitkommaausnahmen auszulösen *Ausnahme*.   Die **Feraiseexcept** -Funktion unterstützt diese definierten Ausnahmemakros \<fenv.h >:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Die *Ausnahme* Argument kann NULL sein, eines der ausnahmemakrowerte oder das bitweise OR von mindestens zwei der unterstützten Ausnahmemakros. Wenn eines der angegebenen Ausnahmemakros FE_OVERFLOW oder FE_UNDERFLOW ist, kann die Ausnahme FE_INEXACT als Nebeneffekt ausgelöst werden.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

**Microsoft Specific:** im angegebenen Ausnahmen *Ausnahme* werden ausgelöst, in der Reihenfolge FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT. Allerdings FE_INEXACT ausgelöst werden kann, wenn FE_OVERFLOW oder FE_UNDERFLOW ausgelöst wird, wenn auch nicht in angegeben *Ausnahme*. **Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|*feraiseexcept*|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
