---
title: _flushall | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _flushall
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
- _flushall
dev_langs:
- C++
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 936a0c4c18b36c490f0edfeefa651e21c017e1fc
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="flushall"></a>_flushall

Leert alle Streams und löscht alle Puffer.

## <a name="syntax"></a>Syntax

```C
int _flushall( void );
```

## <a name="return-value"></a>Rückgabewert

**_flushall** gibt die Anzahl der geöffneten Streams (Eingaben und Ausgaben). Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Wird standardmäßig die **_flushall** Funktion schreibt in die entsprechenden Dateien den Inhalt aller Puffer mit geöffneten Ausgabestreams verknüpft sind. Aus allen Puffern, die geöffneten Eingabestreams zugeordnet sind, wird der aktuelle Inhalt gelöscht. (Diese Puffer werden normalerweise vom Betriebssystem verwaltet, das die optimale Zeit zum automatischen Schreiben der Daten auf den Datenträger bestimmt: wenn ein Puffer ist voll, wenn ein Stream geschlossen wird oder wenn ein Programm normal beendet wird, ohne die Streams zu schließen.)

Wenn ein Lesevorgang einen Aufruf folgt **_flushall**, neue Daten werden aus den Eingabedateien in den Puffer gelesen. Alle Streams bleiben nach dem Aufruf von open **_flushall**.

Mit der Datenträgercommitfunktion der Laufzeitbibliothek können Sie sicherstellen, dass wichtige Daten direkt auf den Datenträger anstatt in die Betriebssystempuffer geschrieben werden. Sie können diese Funktion aktivieren, ohne ein vorhandenes Programm umzuschreiben. Verknüpfen Sie hierzu die Objektdateien des Programms mit "Commode.obj". In der resultierenden ausführbaren Datei aufruft, um **_flushall** den Inhalt aller Puffer auf den Datenträger schreiben. Nur **_flushall** und [Fflush](fflush.md) werden von "commode.obj" beeinflusst.

Weitere Informationen zum Steuern der Datenträgercommitfunktion finden Sie unter [Stream-E/A](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) und [_fdopen](fdopen-wfdopen.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_flushall**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_flushall.c
// This program uses _flushall
// to flush all open buffers.

#include <stdio.h>

int main( void )
{
   int numflushed;

   numflushed = _flushall();
   printf( "There were %d streams flushed\n", numflushed );
}
```

```Output
There were 3 streams flushed
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
