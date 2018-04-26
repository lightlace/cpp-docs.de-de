---
title: feclearexcept1 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- feclearexcept
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
- feclearexcept
- fenv/feclearexcept
dev_langs:
- C++
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc980cea3df0b86848f2cad2b2eceb48bfb2f039
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*excepts*<br/>
Die zu löschenden Gleitkommaausnahme-Flags.

## <a name="return-value"></a>Rückgabewert

Gibt NULL, wenn *excepts* NULL ist, oder wenn die angegebenen Ausnahmen wurden erfolgreich gelöscht wurden. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Feclearexcept** Funktion Versuche zum Deaktivieren der Gleitkommawert zeigen Ausnahme Statusflags gemäß *excepts*. Die Funktion unterstützt diese in fenv.h> definierten Ausnahmemakros:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Die *excepts* Argument 0 (null) oder den bitweisen OR von mindestens einem der unterstützten Ausnahmemakros sein. Das Ergebnis von jedem anderen Argumentwert ist nicht definiert.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
