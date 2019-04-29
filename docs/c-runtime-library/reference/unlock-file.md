---
title: _unlock_file
ms.date: 11/04/2016
apiname:
- _unlock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _unlock_file
- unlock_file
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
ms.openlocfilehash: e3d11cbd59ef5846b33908ae6b6c40d7ea6125e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353539"
---
# <a name="unlockfile"></a>_unlock_file

Hebt die Sperre einer Datei auf, sodass andere Prozesse auf die Datei zugreifen können.

## <a name="syntax"></a>Syntax

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>Parameter

*datei*<br/>
Dateihandle.

## <a name="remarks"></a>Hinweise

Die **_unlock_file** Funktion entsperrt angegebene Datei *Datei*. Das Entsperren einer Datei ermöglicht anderen Prozessen den Zugriff auf die Datei. Diese Funktion sollte nicht aufgerufen werden, es sei denn, **_lock_file** hieß früher auf den *Datei* Zeiger. Aufrufen von **_unlock_file** für eine Datei, die nicht gesperrt ist möglicherweise zu einem Deadlock führen. Ein Beispiel finden Sie unter [_lock_file](lock-file.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
