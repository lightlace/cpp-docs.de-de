---
title: _lseek, _lseeki64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _lseeki64
- _lseek
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
- _lseeki64
- _lseek
- lseeki64
dev_langs:
- C++
helpviewer_keywords:
- lseek function
- _lseek function
- _lseeki64 function
- lseeki64 function
- file pointers [C++], moving
- seek file pointers
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 078143613e4e0742789fbcf68841a939d40d7636
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="lseek-lseeki64"></a>_lseek, _lseeki64

Verschiebt einen Dateizeiger zum angegebenen Speicherort.

## <a name="syntax"></a>Syntax

```C
long _lseek(
   int fd,
   long offset,
   int origin
);
__int64 _lseeki64(
   int fd,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor, der auf eine geöffnete Datei verweist.

*offset*<br/>
Anzahl von Bytes von *origin*.

*origin*<br/>
Ursprüngliche Position.

## <a name="return-value"></a>Rückgabewert

**_lseek** gibt den Offset in Bytes, der die neue Position vom Anfang der Datei. **_lseeki64** gibt den Offset in eine 64-Bit-Ganzzahl. Die Funktion gibt – 1 L zur Anzeige ein Fehlers an. Wenn ein ungültiger Parameter übergeben wird, z.B. ein fehlerhafter Dateideskriptor, oder der Wert für *origin* oder die von *offset* festgelegte Position vor dem Anfang der Datei ungültig ist, wird der Handler für ungültige Parameter aufgerufen, so wie unter [Parameter Validation (Parametervalidierung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EBADF** und -1 L zurückgeben. Auf Geräten, die über keine Suchfunktion verfügen (z.B. Terminals oder Drucker), ist der Rückgabewert undefiniert.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_lseek** -Funktion verschiebt den zugeordneten Dateizeiger *fd* an einem neuen Speicherort, der *Offset* Bytes vom *Ursprung*. Der nächste Vorgang für die Datei tritt am neuen Speicherort auf. Das Argument *origin* muss Teil der folgenden Konstante sein, die allesamt in „Stdio.h“ definiert sind.

|*Ursprung* Wert||
|-|-|
**SEEK_SET**|Anfang der Datei
**SEEK_CUR**|Aktuelle Position des Dateizeigers
**SEEK_END**|Ende der Datei

Sie können **_lseek** den Zeiger an einer beliebigen Stelle in einer Datei oder hinter dem Ende der Datei positioniert.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_lseek**|\<io.h>|
|**_lseeki64**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_lseek.c
/* This program first opens a file named lseek.txt.
* It then uses _lseek to find the beginning of the file,
* to find the current position in the file, and to find
* the end of the file.
*/

#include <io.h>
#include <fcntl.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

int main( void )
{
   int fh;
   long pos;               /* Position of file pointer */
   char buffer[10];

   _sopen_s( &fh, "crt_lseek.c_input", _O_RDONLY, _SH_DENYNO, 0 );

   /* Seek the beginning of the file: */
   pos = _lseek( fh, 0L, SEEK_SET );
   if( pos == -1L )
      perror( "_lseek to beginning failed" );
   else
      printf( "Position for beginning of file seek = %ld\n", pos );

   /* Move file pointer a little */
    _read( fh, buffer, 10 );

   /* Find current position: */
   pos = _lseek( fh, 0L, SEEK_CUR );
   if( pos == -1L )
      perror( "_lseek to current position failed" );
   else
      printf( "Position for current position seek = %ld\n", pos );

   /* Set the end of the file: */
   pos = _lseek( fh, 0L, SEEK_END );
   if( pos == -1L )
      perror( "_lseek to end failed" );
   else
      printf( "Position for end of file seek = %ld\n", pos );

   _close( fh );
}
```

### <a name="input-crtlseekcinput"></a>Eingabe: crt_lseek.c_input

```Input
Line one.
Line two.
Line three.
Line four.
Line five.
```

### <a name="output"></a>Ausgabe

```Output
Position for beginning of file seek = 0
Position for current position seek = 10
Position for end of file seek = 57
```

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_tell, _telli64](tell-telli64.md)<br/>
