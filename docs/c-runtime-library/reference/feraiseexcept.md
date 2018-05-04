---
title: feraiseexcept | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfd60612c92f8e3ff542fd22bbf5b4a01f7b7365
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

*excepts*<br/>
Die auszulösenden Gleitkommaausnahmen

## <a name="return-value"></a>Rückgabewert

Wenn alle angegebenen Ausnahmen erfolgreich ausgelöst werden, wird 0 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Feraiseexcept** -Funktion versucht, die Gleitkommaausnahmen gemäß auslösen *excepts*.   Die **Feraiseexcept** -Funktion unterstützt diese Ausnahmemakros in definierten \<fenv.h >:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Die *excepts* Argument NULL ist, ist möglicherweise eine Ausnahme-Makrowerte oder bitweisen oder zwei oder mehr von den unterstützten Ausnahmemakros. Wenn eines der angegebenen Ausnahmemakros FE_OVERFLOW oder FE_UNDERFLOW ist, kann die Ausnahme FE_INEXACT als Nebeneffekt ausgelöst werden.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

**Microsoft-Specific:** die Ausnahmen, die im angegebenen *excepts* ausgelöst werden, in der Reihenfolge FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT. Allerdings FE_INEXACT können werden ausgelöst, wenn FE_OVERFLOW oder FE_UNDERFLOW ausgelöst wird, auch wenn keine Angabe in *excepts*. **Ende Microsoft-spezifisch**

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
