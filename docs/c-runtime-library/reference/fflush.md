---
title: fflush
ms.date: 09/11/2019
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
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
ms.openlocfilehash: 73ef97306f573fba89ba3cdb8000de9db4d10bac
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927434"
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

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**fflush** gibt 0 zurück, wenn der Puffer erfolgreich geleert wurde. Der Wert 0 wird auch dann zurückgegeben, wenn der angegebene Stream über keinen Puffer verfügt oder nur zum Lesen geöffnet wird. Der Rückgabewert von **EOF** weist auf einen Fehler hin.

> [!NOTE]
> Wenn **fflush** **EOF**zurückgibt, sind die Daten möglicherweise aufgrund eines Schreibfehlers verloren gegangen. Beim Einrichten eines kritischen Fehler Handlers ist es am sichersten, die Pufferung mit der **setvbuf** -Funktion zu aktivieren oder e/a-Routinen auf niedriger Ebene, wie z. b. **_open**, **_close**und **_write** , anstelle der Stream-e/a-Funktionen zu verwenden.

## <a name="remarks"></a>Hinweise

Die **fflush** -Funktion leert den Stream- *Stream*. Wenn der Stream im Schreibmodus oder im Updatemodus geöffnet wurde und der letzte Vorgang ein Schreibvorgang war, werden die Inhalte des Streampuffers in die zugrunde liegende Datei bzw. das Gerät geschrieben, und der Puffer wird verworfen. Wenn der Stream im Lesemodus geöffnet wurde, oder wenn der Stream über keinen Puffer verfügt, hat der Befehl **fflush** keine Auswirkung, und jeder Puffer wird beibehalten. Ein-Befehl von **fflush** negiert die Auswirkung eines früheren Aufrufens von **ungetc** für den Datenstrom. Der Stream bleibt nach dem Aufruf geöffnet.

Wenn der Stream **null**ist, ist das Verhalten mit dem Befehl " **fflush** " für jeden geöffneten Stream identisch. Alle im Schreibmodus geöffneten Streams und alle Streams im Updatemodus, in denen der letzte Vorgang ein Schreibvorgang war, werden geleert. Der Aufruf hat keine Auswirkungen auf andere Streams.

Puffer werden normalerweise vom Betriebssystem verwaltet, das den optimalen Zeitpunkt bestimmt, zu dem Daten automatisch auf den Datenträger geschrieben werden: wenn ein Puffer voll ist, wenn ein Stream geschlossen wird oder wenn ein Programm normal beendet wird, ohne den Stream zu schließen. Mit der Datenträgercommitfunktion der Laufzeitbibliothek können Sie sicherstellen, dass wichtige Daten direkt auf den Datenträger anstatt in die Betriebssystempuffer geschrieben werden. Sie können diese Funktion aktivieren, ohne ein vorhandenes Programm umzuschreiben. Verknüpfen Sie hierzu die Objektdateien des Programms mit COMMODE.OBJ. In der resultierenden ausführbaren Datei schreiben Aufrufe von **_flushall** den Inhalt aller Puffer auf den Datenträger. COMMODE. obj wirkt sich nur auf **_flushall** und **fflush** aus.

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
// Compile with: cl /W4 crt_fflush.c
// This sample gets a number from the user, then writes it to a file.
// It ensures the write isn't lost on crash by calling fflush.
#include <stdio.h>

int * crash_the_program = 0;

int main(void)
{
    FILE * my_file;
    errno_t err = fopen_s(&my_file, "myfile.txt", "w");
    if (my_file && !err)
    {
        printf("Write a number: ");

        int my_number = 0;
        scanf_s("%d", &my_number);

        fprintf(my_file, "User selected %d\n", my_number);

        // Write data to a file immediately instead of buffering.
        fflush(my_file);
    
        if (my_number == 5)
        {
            // Without using fflush, no data was written to the file 
            // prior to the crash, so the data is lost.
            *crash_the_program = 5;
        }

        // Normally, fflush is not needed as closing the file will write the buffer.
        // Note that files are automatically closed and flushed during normal termination.
        fclose(my_file);
    }
    return 0;
}
```

```Input
5
```

```myfile.txt
User selected 5
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
