---
title: _fileno
ms.date: 11/04/2016
api_name:
- _fileno
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fileno
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
ms.openlocfilehash: 586e390e100f5dc46a49b99c007016cf23ac68f0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957208"
---
# <a name="_fileno"></a>_fileno

Ruft den Dateideskriptor ab, der einem Stream zugeordnet ist.

## <a name="syntax"></a>Syntax

```C
int _fileno(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**_fileno** gibt den Dateideskriptor zurück. Es gibt keine Fehlerrückgabe. Das Ergebnis ist nicht definiert, wenn der *Stream* keine geöffnete Datei angibt. Wenn Stream **null**ist, ruft **_fileno** den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die Ausführung weiterhin zugelassen wird, gibt diese Funktion -1 zurück und legt **errno** auf **EINVAL** fest.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

> [!NOTE]
> Wenn **stdout** oder **stderr** keinem Ausgabestream zugeordnet ist (z. b. in einer Windows-Anwendung ohne Konsolenfenster), hat der Dateideskriptor den Wert-2 zurückgegeben. In früheren Versionen lautete der zurückgegebene Dateideskriptor -1. Diese Änderung ermöglicht es Anwendungen, diese Bedingung von einem Fehler unterscheiden.

## <a name="remarks"></a>Hinweise

Die **_fileno** -Routine gibt den Dateideskriptor zurück, der derzeit dem *Stream*zugeordnet ist. Diese Routine wird sowohl als Funktion und als Makro implementiert. Weitere Informationen zum Auswählen einer Implementierung finden Sie unter [Empfehlungen für die Wahl zwischen Funktionen und Macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

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
