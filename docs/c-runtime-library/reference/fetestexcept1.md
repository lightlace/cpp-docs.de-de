---
title: fetestexcept
ms.date: 04/05/2018
apiname:
- fetestexcept
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
- fetestexcept
- fenv/fetestexcept
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
ms.openlocfilehash: ed75ab0ff13029f6ec10c1aafbcb7f7b23b46fd6
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521355"
---
# <a name="fetestexcept"></a>fetestexcept

Bestimmt, welche der angegebenen Gleitkommaausnahme-Statusflags momentan festgelegt sind

## <a name="syntax"></a>Syntax

```C
int fetestexcept(
   int excepts
);
```

### <a name="parameters"></a>Parameter

*Ausnahme*<br/>
Bitweiser OR der zu testenden Gleitkomma-Statusflags

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg eine Bitmaske mit einem bitweisen OR der Gleitkommaausnahme-Makros zurück, die den derzeit festgelegten Ausnahmestatusflags entsprechen. Gibt 0 zurück, wenn keine Ausnahmen festgelegt wurden.

## <a name="remarks"></a>Hinweise

Verwenden Sie die Funktion „fetestexcept“, um zu bestimmen, welche Ausnahmen durch einen Gleitkommavorgang ausgelöst wurden. Verwenden der *Ausnahme* Parameter, um welche Gleitkommaausnahme-Flags zum Testen anzugeben. Die **Fetestexcept** -Funktion verwendet, diese definierten Ausnahmemakros \<fenv.h > in *Ausnahme* und der Rückgabewert:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Das angegebene *Ausnahme* Argument kann 0 (null) eines der unterstützten Gleitkommaausnahme-Makros oder das bitweise OR von mindestens zwei der Makros sein. Der Effekt von jedem anderen *Ausnahme* -Argumentwert ist nicht definiert.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>
