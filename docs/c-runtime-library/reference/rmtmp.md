---
title: _rmtmp
ms.date: 11/04/2016
apiname:
- _rmtmp
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
- rmtmp
- _rmtmp
helpviewer_keywords:
- removing temporary files
- _rmtmp function
- files [C++], temporary
- rmtmp function
- files [C++], removing
- temporary files [C++], removing
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
ms.openlocfilehash: bf4f2cff48e8660682fc8a00d10d9a1fe960a6a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357421"
---
# <a name="rmtmp"></a>_rmtmp

Löscht temporäre Dateien.

## <a name="syntax"></a>Syntax

```C

int _rmtmp( void );
```

## <a name="return-value"></a>Rückgabewert

**_rmtmp** gibt die Anzahl der temporären Dateien geschlossen und gelöscht.

## <a name="remarks"></a>Hinweise

Die **_rmtmp** -Funktion bereinigt alle temporären Dateien im aktuellen Verzeichnis. Die Funktion entfernt nur die Dateien, die von erstellten **Tmpfile**; verwenden sie nur im gleichen Verzeichnis, in dem die temporären Dateien erstellt wurden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_rmtmp**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [tmpfile](tmpfile.md).

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_flushall](flushall.md)<br/>
[tmpfile](tmpfile.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
