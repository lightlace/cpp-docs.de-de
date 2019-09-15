---
title: feholdexcept
ms.date: 04/05/2018
api_name:
- feholdexcept
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
- feholdexcept
- fenv/feholdexcept
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
ms.openlocfilehash: bd55a4ed627d731f7246d589d4b74b4173e31d4e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941187"
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

*nach-oben*<br/>
Zeiger auf ein **fenv_t** -Objekt, das eine Kopie der Gleit Komma Umgebung enthalten soll.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) nur dann zurück, wenn die Funktion eine nicht Ende Gleit Komma Ausnahmebehandlung erfolgreich aktivieren kann.

## <a name="remarks"></a>Hinweise

Die **feholdexcept** -Funktion wird verwendet, um den Zustand der aktuellen Gleit Komma Umgebung im **fenv_t** -Objekt zu speichern, auf das von *KV*verwiesen wird, und um festzulegen, dass die Umgebung die Ausführung bei Gleit Komma Ausnahmen nicht unterbricht. Dies wird als ununterbrochener Modus bezeichnet.  Dieser Modus wird fortgesetzt, bis die Umgebung mithilfe von [fesetenv](fesetenv1.md) oder [feupdateenv](feupdateenv.md) wiederhergestellt wird.

Sie können diese Funktion am Anfang einer Unterroutine verwenden, die eine oder mehrere Gleitkommaausnahmen vor dem Aufrufer verbergen muss. Um eine Ausnahme zu melden, können Sie einfach die unerwünschten Ausnahmen löschen, indem Sie " [feclear" außer](feclearexcept1.md) verwenden und dann den nicht-beenden-Modus mit einem Aufrufen von " **feupdateenv**" beenden.

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
