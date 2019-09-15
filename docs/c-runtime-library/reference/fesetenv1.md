---
title: fesetenv
ms.date: 04/05/2018
api_name:
- fesetenv
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
- fesetenv
- fenv/fesetenv
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 155b9f635f6e8c3dc5acb61126f41c49cd32601f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941109"
---
# <a name="fesetenv"></a>fesetenv

Legt die aktuelle Gleitkommaausnahme fest

## <a name="syntax"></a>Syntax

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>Parameter

*nach-oben*<br/>
Zeiger auf ein **fenv_t** -Objekt, das eine Gleit Komma Umgebung enthält, wie durch einen Aufrufen von [fegetenv](fegetenv1.md) oder [feholdexcept](feholdexcept2.md)festgelegt. Sie können auch die standardmäßige Start Gleit Komma Umgebung mithilfe des **FE_DFL_ENV** -Makros angeben.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn die Umgebung erfolgreich eingerichtet wurde. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **fesetenv** -Funktion legt die aktuelle Gleit Komma Umgebung von dem Wert fest, der im **fenv_t** -Objekt gespeichert ist, auf das von *KV*verwiesen wird. Die Gleitkommaumgebung ist ein Satz von Statusflags und Steuermodi, die Gleitkommaberechnungen beeinflussen. Dies beinhaltet das Rundungsverhalten und die Statusflags für Gleitkommaausnahmen.  Wenn " *KV* " nicht **FE_DFL_ENV** ist oder nicht auf ein gültiges **fenv_t** -Objekt verweist, ist das nachfolgende Verhalten nicht definiert.

Durch einen-aufrufsvorgang werden die ausnahmestatusflags festgelegt, die sich im Objekt " *KV* " befinden, aber diese Ausnahmen werden nicht ausgelöst.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
