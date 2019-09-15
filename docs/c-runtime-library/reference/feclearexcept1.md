---
title: feclearexcept1
ms.date: 04/05/2018
api_name:
- feclearexcept
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
- feclearexcept
- fenv/feclearexcept
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
ms.openlocfilehash: 9899d7068a289e7d5f71cb42a8373869d60c3070
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941271"
---
# <a name="feclearexcept"></a>feclearexcept

Versucht, die Gleitkommaausnahme-Flags zu löschen, die durch das Argument angegeben wurden.

## <a name="syntax"></a>Syntax

```C
int feclearexcept(
   int excepts
);
```

### <a name="parameters"></a>Parameter

*ausgenommen*<br/>
Die zu löschenden Gleitkommaausnahme-Flags.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn die *Ausnahme* 0 (null) ist, oder wenn alle angegebenen Ausnahmen erfolgreich gelöscht wurden. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die Funktion " **feclearaußer** " versucht, die von " *excepts*" angegebenen Gleit Komma Ausnahme-Statusflags zu löschen. Die Funktion unterstützt diese in fenv.h> definierten Ausnahmemakros:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALL_EXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Das *excepts* -Argument kann NULL oder das bitweise OR von mindestens einem der unterstützten Ausnahme Makros sein. Das Ergebnis von jedem anderen Argumentwert ist nicht definiert.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
