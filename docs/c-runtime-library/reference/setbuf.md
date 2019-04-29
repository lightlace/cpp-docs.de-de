---
title: setbuf
ms.date: 04/08/2019
apiname:
- setbuf
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
- setbuf
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
ms.openlocfilehash: 89f8a4d8eb853c774f4f7299ceaa9b9eb6177b42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356388"
---
# <a name="setbuf"></a>setbuf

Steuert die Streampufferung. Diese Funktion ist veraltet. Verwenden Sie stattdessen [setvbuf](setvbuf.md).

## <a name="syntax"></a>Syntax

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

*buffer*<br/>
Vom Benutzer zugewiesener Puffer.

## <a name="remarks"></a>Hinweise

Die **Setbuf** -Funktion steuert die Pufferung für *Stream*. Die *Stream* -Argument muss auf eine geöffnete Datei, die gelesen oder geschrieben wurde noch nicht verweisen. Wenn die *Puffer* Argument **NULL**, der Stream wird ungepufferten. Wenn nicht, der Puffer auf ein Zeichenarray der Länge zeigen muss **BUFSIZ**, wobei **BUFSIZ** in STDIO definiert die Größe des Puffers entspricht. H. Für den E/A-Pufferbetrieb wird anstelle des systemseitig für den gegebenen Stream reservierten Puffers der vom Benutzer angegebene Puffer verwendet. Die **"stderr"** Stream wird ungepufferten standardmäßig, jedoch können Sie **Setbuf** Puffer zuweisen **"stderr"**.

**Setbuf** wurde ersetzt durch [Setvbuf](setvbuf.md), dies ist die bevorzugte Routine für neuen Code. Im Gegensatz zu **Setvbuf**, **Setbuf** hat keine Möglichkeit, Fehler melden. **Setvbuf** auch können Sie steuern, sowohl der Puffermodus als auch die Größe des Puffers. **Setbuf** für Kompatibilität mit vorhandenem Code vorhanden ist.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**setbuf**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_setbuf.c
// compile with: /W3
// This program first opens files named DATA1 and
// DATA2. Then it uses setbuf to give DATA1 a user-assigned
// buffer and to change DATA2 so that it has no buffer.

#include <stdio.h>

int main( void )
{
   char buf[BUFSIZ];
   FILE *stream1, *stream2;

   fopen_s( &stream1, "data1", "a" );
   fopen_s( &stream2, "data2", "w" );

   if( (stream1 != NULL) && (stream2 != NULL) )
   {
      // "stream1" uses user-assigned buffer:
      setbuf( stream1, buf ); // C4996
      // Note: setbuf is deprecated; consider using setvbuf instead
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );

      // "stream2" is unbuffered
      setbuf( stream2, NULL ); // C4996
      printf( "stream2 buffering disabled\n" );
      _fcloseall();
   }
}
```

```Output
stream1 set to user-defined buffer at: 0012FCDC
stream2 buffering disabled
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
