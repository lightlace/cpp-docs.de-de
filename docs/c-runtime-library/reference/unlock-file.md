---
title: _unlock_file
ms.date: 11/04/2016
api_name:
- _unlock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _unlock_file
- unlock_file
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
ms.openlocfilehash: 2983408f066ea00c0b7ab111d9a6349700ecaece
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957477"
---
# <a name="_unlock_file"></a>_unlock_file

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

Die **_unlock_file** -Funktion entsperrt die Datei, die in der *Datei*angegeben ist. Das Entsperren einer Datei ermöglicht anderen Prozessen den Zugriff auf die Datei. Diese Funktion sollte nur aufgerufen werden, wenn **_lock_file** zuvor für den *Datei* Zeiger aufgerufen wurde. Das Aufrufen von **_unlock_file** für eine Datei, die nicht gesperrt ist, kann zu einem Deadlock führen. Ein Beispiel finden Sie unter [_lock_file](lock-file.md).

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
