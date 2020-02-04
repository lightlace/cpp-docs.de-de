---
title: fegetexceptflag
ms.date: 04/05/2018
api_name:
- fegetexceptflag
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
- fegetexceptflag
- fenv/fegetexceptflag
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
ms.openlocfilehash: b840408ce704ad5519fbf233de41c8d5422006ad
ms.sourcegitcommit: ba4180a2d79d7e391f2f705797505d4aedbc2a5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "76972188"
---
# <a name="fegetexceptflag"></a>fegetexceptflag

Speichert den aktuellen Zustand der angegebenen Gleitkommaausnahme-Flags.

## <a name="syntax"></a>Syntax

```C
int fegetexceptflag(
   fexcept_t* pstatus,
   int excepts
);
```

### <a name="parameters"></a>Parameters

*pstatus*<br/>
Ein Zeiger auf ein **fexcept_t** Objekt, das die aktuellen Werte der von *excepts*angegebenen ausnahmeflags enthalten soll.

*ausgenommen*<br/>
Die Gleit Komma Ausnahme-Flags, die in *pstatus*gespeichert werden sollen.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg wird 0 zurückgegeben. Andernfalls wird ein Wert ungleich null zurückgegeben.

## <a name="remarks"></a>Hinweise

Die Funktion " **fegetexceptflag** " speichert den aktuellen Zustand der Gleit Komma Ausnahme-Statusflags, die durch " *excepts* " in dem **fexcept_t** Objekt angegeben werden, auf das *pstatus*zeigt.  *pstatus* muss auf ein gültiges **fexcept_t** Objekt zeigen, oder das nachfolgende Verhalten ist nicht definiert. Die Funktion " **fegetexceptflag** " unterstützt diese Ausnahme Makros, die in \<fenv. h-> definiert sind:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALL_EXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Das *excepts* -Argument kann 0 (null), eines der unterstützten Gleit Komma Ausnahme-Makros oder das bitweise OR von mindestens zwei Makros sein. Der Effekt von jedem anderen Argumentwert ist nicht definiert.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>-Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fegetexceptflag**|\<fenv.h>|\<cfenv>|

Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
