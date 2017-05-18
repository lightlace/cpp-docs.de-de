---
title: fseek, _fseeki64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fseeki64
- fseek
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
apitype: DLLExport
f1_keywords:
- fseek
- _fseeki64
dev_langs:
- C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 0d0c0bf620f1b89b9decceed3db9434dae4f9437
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64
Verschiebt den Dateizeiger in einen angegebenen Speicherort  
  
## <a name="syntax"></a>Syntax  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
 `offset`  
 Anzahl der Bytes aus `origin`  
  
 `origin`  
 Ursprüngliche Position  
  
## <a name="return-value"></a>Rückgabewert  
 `fseek` und `_fseeki64` geben bei Erfolg 0 zurück. Andernfalls gibt es einen Wert ungleich 0 (null) zurück. Auf Geräten, die Suchvorgänge nicht unterstützen, ist der Rückgabewert nicht definiert. Wenn `stream` ein NULL-Zeiger oder `origin` keiner der unten beschriebenen, zugelassenen Werte ist, rufen `fseek` und `_fseeki64` den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben -1 zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `fseek` und `_fseeki64` verschiebt der Dateizeiger (sofern vorhanden) zugeordneten Funktionen `stream` an einem neuen Speicherort, der `offset` Bytes vom `origin`. Der nächste Vorgang im Stream tritt am neuen Speicherort auf. Für einen updatebereiten Stream kann der nächste Vorgang ein Lese- oder Schreibvorgang sein. Das Argument „origin“ muss Teil der folgenden Konstanten sein, die in STDIO.H definiert sind:  
  
 `SEEK_CUR`  
 Aktuelle Position des Dateizeigers  
  
 `SEEK_END`  
 Ende der Datei  
  
 `SEEK_SET`  
 Anfang der Datei  
  
 Sie können `fseek` und `_fseeki64` verwenden, um den Zeiger an einer beliebigen Stelle in einer Datei neu zu positionieren. Der Zeiger kann auch nach dem Ende der Datei positioniert werden. `fseek`und `_fseeki64` löscht den Dateiende-Indikator und neutralisiert die Wirkung der vorherige `ungetc` gegen ruft `stream`.  
  
 Wenn eine Datei zum Anfügen von Daten geöffnet wird, wird die aktuelle Dateiposition vom letzten E/A-Vorgang nicht dadurch bestimmt, wo der nächste Schreibvorgang erfolgt. Wenn noch kein E/A-Vorgang für eine zum Anhängen geöffnete Datei stattgefunden hat, ist die Dateiposition der Anfang der Datei.  
  
 Für Streams, die im Textmodus geöffnet `fseek` und `_fseeki64` verwenden, haben beschränkt werden, da Carriage Return-Zeilenvorschub Übersetzungen können dazu führen, dass `fseek` und `_fseeki64` zu unerwarteten Ergebnissen führen. Die einzige `fseek` und `_fseeki64` Vorgänge im Textmodus geöffnet Datenstreams funktioniert auf alle Fälle sind:  
  
-   Suchen mit einem Offset von 0 hinsichtlich der ursprünglichen Werte  
  
-   Suchvorgänge vom Anfang der Datei mit einem Offset-Wert zurückgegeben, Aufrufen von `ftell` Verwendung `fseek` oder `_ftelli64` Verwendung `_fseeki64`.  
  
 Im Textmodus wird STRG+Z als ein Dateiendezeichen in der Eingabe interpretiert. In für Lese-/Schreibvorgänge geöffneten Dateien, überprüfen `fopen` und alle verknüpften Routinen das Dateiende auf STRG+Z und entfernt die Markierung, sofern möglich. Dies geschieht, da die Verwendung von `fseek` und `ftell` oder `_fseeki64` und `_ftelli64` zum Navigieren innerhalb einer Datei, die mit Strg+Z endet, dazu führen kann, dass sich `fseek` und `_fseeki64` in der Nähe des Dateiendes nicht ordnungsgemäß verhalten.  
  
 Wenn CRT eine Datei öffnet, die mit einer Bytereihenfolge-Marke (Byte Order Mark, BOM) beginnt, wird der Dateizeiger nach der BOM positioniert (d.h. am Anfang des tatsächlichen Dateiinhalts). Wenn Sie `fseek` am Dateianfang verwenden müssen, verwenden Sie `ftell`, um die ursprüngliche Position abzurufen, und wenden Sie `fseek` darauf an, anstatt auf Position 0.  
  
 Diese Funktion sperrt alle anderen Threads während der Ausführung und ist daher threadsicher. Eine nicht sperrende Version finden Sie unter [_fseek_nolock, _fseeki64_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fseek`|\<stdio.h>|  
|`_fseeki64`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
```Output  
File pointer is set to middle of first line.  
This is the file 'fseek.out'.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, _ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)
