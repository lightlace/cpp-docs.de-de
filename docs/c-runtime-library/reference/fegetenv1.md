---
title: fegetenv
ms.date: 04/05/2018
api_name:
- fetegenv
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
- fegetenv
- fenv/fegetenv
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
ms.openlocfilehash: b2e3566eb96174d0f0ccd6beb401824cc052c995
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941244"
---
# <a name="fegetenv"></a>fegetenv

Speichert die aktuelle Gleitkommaumgebung in das angegebene Objekt.

## <a name="syntax"></a>Syntax

```C
int fegetenv(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parameter

*nach-oben*<br/>
Zeiger auf ein **fenv_t** -Objekt, das die aktuellen Gleit Komma Umgebungs Werte enthalten soll.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn die Gleit Komma Umgebung *erfolgreich in der*-Datei gespeichert wurde. Andernfalls wird ein Wert ungleich null zurückgegeben.

## <a name="remarks"></a>Hinweise

Die Funktion " **fegetenv** " speichert die aktuelle Gleit Komma Umgebung in dem Objekt, auf das von " *KV*" verwiesen wird. Die Gleitkommaumgebung ist ein Satz von Statusflags und Steuermodi, die Gleitkommaberechnungen beeinflussen. Darunter fallen auch das Rundungsverhalten und die Statusflags für Gleitkommaausnahmen.  Wenn " *KV* " nicht auf ein gültiges **fenv_t** -Objekt verweist, ist das nachfolgende Verhalten nicht definiert.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
