---
title: _fileno | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fileno
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
- _fileno
dev_langs:
- C++
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9bc03bcd92eb8040b7eefadd0c109e4e887f7304
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398864"
---
# <a name="fileno"></a>_fileno

Ruft den Dateideskriptor ab, der einem Stream zugeordnet ist.

## <a name="syntax"></a>Syntax

```C
int _fileno(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**_fileno** gibt den Dateideskriptor zurück. Es gibt keine Fehlerrückgabe. Das Ergebnis ist undefiniert, wenn *Stream* gibt keine geöffneten Datei. Wenn der Stream ist **NULL**, **_fileno** wird den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion gibt-1 zurück und setzt **Errno** auf **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

> [!NOTE]
> Wenn **"stdout"** oder **"stderr"** ist nicht verknüpft mit einen Ausgabestream (z. B. in einer Windows-Anwendung ohne ein Konsolenfenster), ist der zurückgegebenen Dateideskriptor-2. In früheren Versionen lautete der zurückgegebene Dateideskriptor -1. Diese Änderung ermöglicht es Anwendungen, diese Bedingung von einem Fehler unterscheiden.

## <a name="remarks"></a>Hinweise

Die **_fileno** Routine gibt zurück, den aktuell zugeordneten Dateideskriptor *Stream*. Diese Routine wird sowohl als Funktion und als Makro implementiert. Weitere Informationen zum Auswählen einer Implementierung finden Sie unter [Empfehlungen für die Wahl zwischen Funktionen und Macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fileno**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fileno.c
// This program uses _fileno to obtain
// the file descriptor for some standard C streams.
//

#include <stdio.h>

int main( void )
{
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );
}
```

```Output
The file descriptor for stdin is 0
The file descriptor for stdout is 1
The file descriptor for stderr is 2
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
