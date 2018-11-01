---
title: setvbuf
ms.date: 11/04/2016
apiname:
- setvbuf
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
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: b2a5cfc08da7812e32ad84940ab4c78288017720
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445772"
---
# <a name="setvbuf"></a>setvbuf

Steuert die Streampufferung und die Puffergröße.

## <a name="syntax"></a>Syntax

```C
int setvbuf(
   FILE *stream,
   char *buffer,
   int mode,
   size_t size
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

*buffer*<br/>
Vom Benutzer zugewiesener Puffer.

*mode*<br/>
Pufferungsmodus.

*size*<br/>
Puffergröße in Bytes. Zulässiger Bereich: 2 < = *Größe* < = INT_MAX (2147483647). Intern für die angegebene Wert *Größe* wird auf das nächste Vielfache von 2 abgerundet.

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg 0 zurück.

Wenn *Stream* ist **NULL**, oder wenn *Modus* oder *Größe* wird nicht aus einem gültigen, Handler für ungültige Parameter wird aufgerufen, wie in beschrieben. [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, diese Funktion gibt-1 zurück und legt **Errno** zu **EINVAL**.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Setvbuf** -Funktion ermöglicht dem Programm zu steuern, Pufferung und die Puffergröße für *Stream*. *Stream* muss verweisen auf eine geöffnete Datei, die keinen e/a-Vorgang vorgenommen wurden, seitdem sie geöffnet wurde. Das Array verweist *Puffer* dient als Puffer, es sei denn, es ist **NULL**, in diesem Fall **Setvbuf** verwendet einen automatisch zugewiesenen Puffer der Länge  *Größe*/2 \* 2 Byte.

Der Modus muss **_IOFBF**, **_IOLBF**, oder **_IONBF**. Wenn *Modus* ist **_IOFBF** oder **_IOLBF**, klicken Sie dann *Größe* als die Größe des Puffers verwendet wird. Wenn *Modus* ist **_IONBF**, der Stream wird ungepufferten und *Größe* und *Puffer* werden ignoriert. Werte für *Modus* und ihre Bedeutung sind:

|*Modus* Wert|Bedeutung|
|-|-|
**_IOFBF**|Vollständige Pufferung; d. h. *Puffer* dient als Puffer und *Größe* als die Größe des Puffers verwendet wird. Wenn *Puffer* ist **NULL**, ein automatisch zugewiesener Puffer *Größe* Byte verwendet wird.
**_IOLBF**|Für einige Systeme bietet dies Zeilenpufferung. Allerdings für Win32 ist das Verhalten identisch mit **_IOFBF** – vollständige Pufferung.
**_IONBF**|Kein Puffer wird verwendet, unabhängig von *Puffer* oder *Größe*.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_setvbuf.c
// This program opens two streams: stream1
// and stream2. It then uses setvbuf to give stream1 a
// user-defined buffer of 1024 bytes and stream2 no buffer.
//

#include <stdio.h>

int main( void )
{
   char buf[1024];
   FILE *stream1, *stream2;

   if( fopen_s( &stream1, "data1", "a" ) == 0 &&
       fopen_s( &stream2, "data2", "w" ) == 0 )
   {
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )
         printf( "Incorrect type or size of buffer for stream1\n" );
      else
         printf( "'stream1' now has a buffer of 1024 bytes\n" );
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )
         printf( "Incorrect type or size of buffer for stream2\n" );
      else
         printf( "'stream2' now has no buffer\n" );
      _fcloseall();
   }
}
```

```Output
'stream1' now has a buffer of 1024 bytes
'stream2' now has no buffer
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
