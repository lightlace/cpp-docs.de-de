---
title: _commit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _commit
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _commit
- commit
dev_langs:
- C++
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e9bc746c347bfb60fb78edbf025b676f8218c66
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394830"
---
# <a name="commit"></a>_commit

Leert eine Datei direkt auf den Datenträger.

## <a name="syntax"></a>Syntax

```C
int _commit(
   int fd
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor, der auf die geöffnete Datei verweist.

## <a name="return-value"></a>Rückgabewert

**_commit** gibt 0 zurück, wenn die Datei erfolgreich wurde auf den Datenträger geleert. Ein Rückgabewert von – 1 zeigt einen Fehler.

## <a name="remarks"></a>Hinweise

Die **_commit** Funktion erzwingt, dass das Betriebssystem zum Schreiben der Datei zugeordneten *fd* auf den Datenträger. Dieser Aufruf stellt sicher, dass die angegebene Datei sofort geleert wird (und nicht nach Ermessen des Betriebssystems).

Wenn *fd* ist ein ungültiger Dateideskriptor Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion-1 zurück und **Errno** festgelegt ist, um **EBADF**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionale Header|
|-------------|---------------------|----------------------|
|**_commit**|\<io.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_write](write.md)<br/>
