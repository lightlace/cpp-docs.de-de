---
title: Fetestexcept | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0450fcaddf8ca05484d0b2bd122ff006eb8355f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

*excepts*<br/>
Bitweiser OR der zu testenden Gleitkomma-Statusflags

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg eine Bitmaske mit einem bitweisen OR der Gleitkommaausnahme-Makros zurück, die den derzeit festgelegten Ausnahmestatusflags entsprechen. Gibt 0 zurück, wenn keine Ausnahmen festgelegt wurden.

## <a name="remarks"></a>Hinweise

Verwenden Sie die Funktion „fetestexcept“, um zu bestimmen, welche Ausnahmen durch einen Gleitkommavorgang ausgelöst wurden. Verwenden der *excepts* Parameter an, welche Ausnahme Statusflags zu testen. Die **Fetestexcept** -Funktion verwendet diese Ausnahmemakros in definierten \<fenv.h > in *excepts* und der Rückgabewert:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Das angegebene *excepts* Argument möglicherweise 0, einem der unterstützten Gleitkommaausnahme Makros oder bitweisen oder von zwei oder mehr der Makros. Die Auswirkung eines anderen *excepts* Argumentwert ist nicht definiert.

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
