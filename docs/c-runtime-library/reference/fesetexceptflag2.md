---
title: Fesetexceptflag | Microsoft Docs
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
- fesetexceptflag
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
- fesetexceptflag
- fenv/fesetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec9be76fd0d860385ac53cfc70ea89d00ae2b1ef
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="fesetexceptflag"></a>fesetexceptflag

Legt die angegebenen Gleitkomma-Statusflags in der aktuellen Gleitkommaumgebung fest

## <a name="syntax"></a>Syntax

```C
int fesetexceptflag(
     const fexcept_t *pstatus,
     int excepts
);
```

### <a name="parameters"></a>Parameter

*pstatus*<br/>
Zeiger auf eine **Fexcept_t** Objekt mit den Werten, die Ausnahme Statusflags festgelegt werden soll. Das Objekt kann auf einen früheren Aufruf von [fegetexceptflag](fegetexceptflag2.md) festgelegt werden .

*excepts*<br/>
Die festzulegenden Gleitkommaausnahme-Statusflags

## <a name="return-value"></a>Rückgabewert

Wenn alle angegebenen Ausnahmestatusflags erfolgreich festgelegt wurden, wird 0 zurückgegeben. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Fesetexceptflag** Funktion legt den Status der Gleitkommaausnahme Status-Markierungen gemäß *excepts* auf die entsprechenden Werte festgelegt werden, der **Fexcept_t** Objekt verweist *Pstatus*.  Es löst die Ausnahmen aber nicht aus. Die *Pstatus* Zeiger muss einem gültigen zeigen **Fexcept_t** Objekt oder nachfolgenden Verhalten ist nicht definiert. Die **Fesetexceptflag** -Funktion unterstützt diese Ausnahme-Makrowerte im *excepts*in definierte \<fenv.h >:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Die *excepts* Argument NULL ist, werden möglicherweise einem der unterstützten Gleitkommaausnahme Makros oder bitweisen oder zwei oder mehr der Makros. Der Effekt von jedem anderen Argumentwert ist nicht definiert.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fesetexceptflag**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fegetexceptflag](fegetexceptflag2.md)<br/>
