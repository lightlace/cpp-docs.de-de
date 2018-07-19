---
title: _dup, _dup2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _dup
- _dup2
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
- _dup2
- _dup
dev_langs:
- C++
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad477dc09ce6c8bee2d69e479f8e1615639cb14d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399802"
---
# <a name="dup-dup2"></a>_dup, _dup2

Erstellt einen zweiten Dateideskriptor für eine geöffnete Datei (**_dup**), oder weist einen Dateideskriptor (**_dup2**).

## <a name="syntax"></a>Syntax

```C
int _dup( int fd );
int _dup2( int fd1, int fd2 );
```

### <a name="parameters"></a>Parameter

*Fd*, *fd1*<br/>
Dateideskriptoren, die auf die geöffnete Datei verweisen.

*FD2*<br/>
Jeder beliebige Dateideskriptor.

## <a name="return-value"></a>Rückgabewert

**_dup** gibt einen neuen Dateideskriptor zurück. **_dup2** gibt 0, um einen Erfolg zu melden. Wenn ein Fehler auftritt, jede Funktion gibt-1 zurück und legt **Errno** auf **EBADF** , wenn der Dateideskriptor ungültig ist oder auf **EMFILE** , wenn keine weiteren Dateideskriptoren verfügbar sind. Bei einem ungültigen Dateideskriptor ruft die Funktion auch den Handler für ungültige Parameter auf, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_dup** und **_dup2** Funktionen ordnen einen zweiten Dateideskriptor einer momentan geöffneten Datei. Diese Funktionen können verwendet werden, um einen vordefinierten Dateideskriptor – wie z. B. zuzuordnen **"stdout"**, mit einer anderen Datei. Das Durchführen von Operationen an der Datei ist mit jedem der beiden Dateideskriptoren möglich. Der für die Datei zulässige Zugriffstyp ist von der Erstellung eines neuen Deskriptors nicht betroffen. **_dup** gibt den nächsten verfügbaren Dateideskriptor für die angegebene Datei zurück. **_dup2** erzwingt *fd2* zum Verweisen auf dieselbe Datei wie *fd1*. Wenn *fd2* ist verknüpft mit einer geöffneten Datei zum Zeitpunkt des Aufrufs, diese Datei geschlossen.

Beide **_dup** und **_dup2** akzeptieren Dateideskriptoren als Parameter. Einen Datenstrom übergeben (**Datei \*** ) verwenden, um beide Varianten dieser Funktionen [_fileno](fileno.md). Die **Fileno** Routine gibt den Dateideskriptor derzeit zugewiesen ist, mit dem angegebenen Stream. Im folgende Beispiel wird gezeigt, wie zuzuordnende **"stderr"** (definiert als **Datei \***  in Stdio.h) einem Dateideskriptor:

```C
int cstderr = _dup( _fileno( stderr ));
```

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_dup**|\<io.h>|
|**_dup2**|\<io.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_dup.c
// This program uses the variable old to save
// the original stdout. It then opens a new file named
// DataFile and forces stdout to refer to it. Finally, it
// restores stdout to its original state.

#include <io.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int old;
   FILE *DataFile;

   old = _dup( 1 );   // "old" now refers to "stdout"
                      // Note:  file descriptor 1 == "stdout"
   if( old == -1 )
   {
      perror( "_dup( 1 ) failure" );
      exit( 1 );
   }
   _write( old, "This goes to stdout first\n", 26 );
   if( fopen_s( &DataFile, "data", "w" ) != 0 )
   {
      puts( "Can't open file 'data'\n" );
      exit( 1 );
   }

   // stdout now refers to file "data"
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )
   {
      perror( "Can't _dup2 stdout" );
      exit( 1 );
   }
   puts( "This goes to file 'data'\n" );

   // Flush stdout stream buffer so it goes to correct file
   fflush( stdout );
   fclose( DataFile );

   // Restore original stdout
   _dup2( old, 1 );
   puts( "This goes to stdout\n" );
   puts( "The file 'data' contains:" );
   _flushall();
   system( "type data" );
}
```

```Output
This goes to stdout first
This goes to stdout

The file 'data' contains:
This goes to file 'data'
```

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
