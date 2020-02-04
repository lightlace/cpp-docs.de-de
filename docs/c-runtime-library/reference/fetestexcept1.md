---
title: fetestexcept
ms.date: 04/05/2018
api_name:
- fetestexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fetestexcept
- fenv/fetestexcept
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
ms.openlocfilehash: e70ae1b74420b8186cccd8fc8a817423df618adf
ms.sourcegitcommit: ba4180a2d79d7e391f2f705797505d4aedbc2a5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "76972163"
---
# <a name="fetestexcept"></a>fetestexcept

Bestimmt, welche der angegebenen Gleitkommaausnahme-Statusflags momentan festgelegt sind

## <a name="syntax"></a>Syntax

```C
int fetestexcept(
   int excepts
);
```

### <a name="parameters"></a>Parameters

*ausgenommen*<br/>
Bitweiser OR der zu testenden Gleitkomma-Statusflags

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg eine Bitmaske mit einem bitweisen OR der Gleitkommaausnahme-Makros zurück, die den derzeit festgelegten Ausnahmestatusflags entsprechen. Gibt 0 zurück, wenn keine Ausnahmen festgelegt wurden.

## <a name="remarks"></a>Hinweise

Verwenden Sie die Funktion „fetestexcept“, um zu bestimmen, welche Ausnahmen durch einen Gleitkommavorgang ausgelöst wurden. Verwenden Sie den *Exception* -Parameter, um anzugeben, welche ausnahmestatusflags getestet werden sollen. Die Funktion **fetestwith** verwendet diese Ausnahme Makros, die in \<fenv. *h->* definiert sind, und gibt den Rückgabewert zurück:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALL_EXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Das angegebene *excepts* -Argument kann 0, eines der unterstützten Gleit Komma Ausnahme-Makros oder das bitweise OR von mindestens zwei Makros sein. Die Auswirkung eines beliebigen anderen *excepts* -Argument Werts ist nicht definiert.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>-Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv.h>|\<cfenv>|

Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>
