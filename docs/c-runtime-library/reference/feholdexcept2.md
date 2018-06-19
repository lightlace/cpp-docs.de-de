---
title: Feholdexcept | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- feholdexcept
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
- feholdexcept
- fenv/feholdexcept
dev_langs:
- C++
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6250de98b2eb3f8cc8c475d341c1d63a79262362
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397541"
---
# <a name="feholdexcept"></a>feholdexcept

Speichert die aktuelle Gleitkommaumgebung im angegebenen Objekt, löscht die Gleitkomma-Statusflags und setzt die Gleitkommaumgebung wenn möglich in den ununterbrochenen Modus.

## <a name="syntax"></a>Syntax

```C
int feholdexcept(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parameter

*penv*<br/>
Zeiger auf eine **Fenv_t** Objekt, das eine Kopie der Gleitkomma-Umgebung enthalten.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn die Funktion erfolgreich unterbrechungsfreier Gleitkommaausnahmen behandeln aktivieren kann.

## <a name="remarks"></a>Hinweise

Die **Feholdexcept** Funktion dient zum Speichern des Zustands der aktuellen floating Point-Umgebung in der **Fenv_t** Objekt verweist *Penv*, und klicken Sie auf die Umgebung festgelegt werden soll Unterbrechen Sie nicht die Ausführung auf Gleitkommaausnahmen. Dies wird als ununterbrochener Modus bezeichnet.  Dieser Modus wird fortgesetzt, bis die Umgebung mithilfe von [fesetenv](fesetenv1.md) oder [feupdateenv](feupdateenv.md) wiederhergestellt wird.

Sie können diese Funktion am Anfang einer Unterroutine verwenden, die eine oder mehrere Gleitkommaausnahmen vor dem Aufrufer verbergen muss. Um eine Ausnahme zu melden, können Sie einfach das unbeabsichtigten Ausnahmen löschen, indem [Feclearexcept,](feclearexcept1.md) und beenden Sie den Modus "nicht beenden" mit einem Aufruf von **Feupdateenv**.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
