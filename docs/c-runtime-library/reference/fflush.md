---
title: fflush | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fflush
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
- fflush
dev_langs:
- C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a92affa1483c8dba9be0718acc00d4574eb44bb
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="fflush"></a>fflush

Leert einen Stream

## <a name="syntax"></a>Syntax

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**Fflush** gibt 0 zurück, wenn der Puffer erfolgreich geleert wurde. Der Wert 0 wird auch dann zurückgegeben, wenn der angegebene Stream über keinen Puffer verfügt oder nur zum Lesen geöffnet wird. Ein Rückgabewert von **EOF** zeigt einen Fehler an.

> [!NOTE]
> Wenn **Fflush** gibt **EOF**, Daten verloren gegangen aufgrund ein Schreibfehler auftritt. Bei der ein schwerwiegender Fehlerhandler einrichten, ist es am sichersten, deaktivieren Sie Pufferung mit der **Setvbuf** Funktion oder e/a-Routine auf niedriger Ebene verwenden, z. B. **_open**, **_close**, und **_write** anstelle der-e/a-streamfunktionen.

## <a name="remarks"></a>Hinweise

Die **Fflush** Funktion entleert den Stream *Stream*. Wenn der Stream im Schreibmodus oder im Updatemodus geöffnet wurde und der letzte Vorgang ein Schreibvorgang war, werden die Inhalte des Streampuffers in die zugrunde liegende Datei bzw. das Gerät geschrieben, und der Puffer wird verworfen. Wenn der Stream im Lesemodus geöffnet wurde oder wenn der Stream keine Puffer, der Aufruf von enthält **Fflush** hat keine Auswirkungen, und alle Puffer wird beibehalten. Ein Aufruf von **Fflush** neutralisiert die Wirkung des vorherigen Aufrufs zum **Ungetc** für den Stream. Der Stream bleibt nach dem Aufruf geöffnet.

Wenn *Stream* ist **NULL**, das Verhalten ist identisch mit einem Aufruf von **Fflush** zu den einzelnen geöffneten Streams. Alle im Schreibmodus geöffneten Streams und alle Streams im Updatemodus, in denen der letzte Vorgang ein Schreibvorgang war, werden geleert. Der Aufruf hat keine Auswirkungen auf andere Streams.

Puffer werden normalerweise vom Betriebssystem verwaltet, das den optimalen Zeitpunkt bestimmt, zu dem Daten automatisch auf den Datenträger geschrieben werden: wenn ein Puffer voll ist, wenn ein Stream geschlossen wird oder wenn ein Programm normal beendet wird, ohne den Stream zu schließen. Mit der Datenträgercommitfunktion der Laufzeitbibliothek können Sie sicherstellen, dass wichtige Daten direkt auf den Datenträger anstatt in die Betriebssystempuffer geschrieben werden. Sie können diese Funktion aktivieren, ohne ein vorhandenes Programm umzuschreiben. Verknüpfen Sie hierzu die Objektdateien des Programms mit COMMODE.OBJ. In der resultierenden ausführbaren Datei aufruft, um **_flushall** den Inhalt aller Puffer auf den Datenträger schreiben. Nur **_flushall** und **Fflush** werden von "commode.obj" beeinflusst.

Weitere Informationen zum Steuern der Datenträgercommitfunktion finden Sie unter [Stream-E/A](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) und [_fdopen](fdopen-wfdopen.md).

Diese Funktion sperrt den aufrufenden Thread und ist threadsicher. Eine nicht sperrende Version finden Sie unter **_fflush_nolock**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fflush**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fflush.c
#include <stdio.h>
#include <conio.h>

int main( void )
{
   int integer;
   char string[81];

   // Read each word as a string.
   printf( "Enter a sentence of four words with scanf: " );
   for( integer = 0; integer < 4; integer++ )
   {
      scanf_s( "%s", string, sizeof(string) );
      printf( "%s\n", string );
   }

   // You must flush the input buffer before using gets.
   // fflush on input stream is an extension to the C standard
   fflush( stdin );
   printf( "Enter the same sentence with gets: " );
   gets_s( string, sizeof(string) );
   printf( "%s\n", string );
}
```

```Output

      This is a test
This is a test

```

```Output

      This is a test
This is a testEnter a sentence of four words with scanf: This is a test
This
is
a
test
Enter the same sentence with gets: This is a test
This is a test
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
