---
title: ftell, _ftelli64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs: C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: df0feee9beb2b2fc5144974f1fc06ff2b8d02b80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64
Ruft die aktuelle Position eines Dateizeigers ab  
  
## <a name="syntax"></a>Syntax  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zielstruktur von `FILE`  
  
## <a name="return-value"></a>Rückgabewert  
 `ftell` und `_ftelli64` geben die aktuelle Dateiposition zurück. Der Rückgabewert von `ftell` und `_ftelli64` entsprechen möglicherweise nicht der physischen Byteoffset für Streams, die im Textmodus geöffnet, weil Textmodus Carriage Return-Zeilenvorschub Übersetzung verursacht. Verwendung `ftell` mit `fseek` oder `_ftelli64` mit `_fseeki64` ordnungsgemäß an der Datei zurückgegeben. Bei Fehler `ftell` und `_ftelli64` Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, diese Funktionen zurück – 1 L und legen `errno` auf eine der beiden Konstanten, die in ERRNO definiert. H. Die `EBADF`-Konstante bedeutet, dass das `stream`-Argument kein gültiger Dateizeigerwert ist oder nicht auf eine geöffnete Datei verweist. `EINVAL` bedeutet, dass ein ungültiges `stream`-Argument an die Funktion übergeben wurde. Auf Geräten, die über keine Suchfunktion verfügen (z.B. Terminals oder Drucker), ist der Rückgabewert undefiniert. Er ist auch undefiniert, wenn `stream` auf keine offene Datei verweist.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `ftell` und `_ftelli64` Funktionen Abrufen die aktuelle Position des Dateizeigers (falls vorhanden) zugeordneten `stream`. Die Position wird als ein Offset relativ zum Anfang des Streams ausgedrückt.  
  
 Beachten Sie, dass wenn eine Datei zum Anfügen von Daten geöffnet wird, die aktuelle Dateiposition vom letzten E/A-Vorgang nicht dadurch bestimmt wird, wo der nächste Schreibvorgang erfolgt. Wenn eine Datei für einen Anfügevorgang geöffnet wird und der letzte Vorgang ein Lesevorgang war, ist die Dateiposition der Punkt, an dem der nächste Lesevorgang gestartet wird, aber nicht der nächste Schreibvorgang. (Wenn eine Datei für einen Anfügevorgang geöffnet wird, wird die Dateiposition vor einem Schreibvorgang an das Ende der Datei verschoben.) Wenn noch kein E/A-Vorgang für eine zum Anhängen geöffnete Datei stattgefunden hat, ist die Dateiposition der Anfang der Datei.  
  
 Im Textmodus wird STRG+Z in der Eingabe als Dateiendezeichen interpretiert. In für Lese-/Schreibvorgänge geöffneten Dateien, überprüfen `fopen` und alle verknüpften Routinen das Dateiende auf STRG+Z und entfernt die Markierung, sofern möglich. Dies geschieht, da die Verwendung von `ftell` und `fseek` oder `_ftelli64` und `_fseeki64` zum Navigieren innerhalb einer Datei, die mit Strg+Z endet, dazu führen kann, dass sich `ftell` und `_ftelli64` in der Nähe des Dateiendes nicht ordnungsgemäß verhalten.  
  
 Diese Funktion sperrt den aufrufenden Thread während der Ausführung und ist threadsicher. Eine nicht sperrende Version finden Sie unter `_ftell_nolock`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|Optionale Header|  
|--------------|---------------------|----------------------|  
|`ftell`|\<stdio.h>|\<errno.h>|  
|`_ftelli64`|\<stdio.h>|\<errno.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
```Output  
Position after trying to read 100 bytes: 100  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)