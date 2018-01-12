---
title: fflush | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: fflush
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
f1_keywords: fflush
dev_langs: C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2692e06416da3b62e5f9e87b4c0827d3003253e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fflush"></a>fflush
Leert einen Stream  
  
## <a name="syntax"></a>Syntax  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `fflush` gibt 0 zurück, wenn der Puffer erfolgreich geleert wurde. Der Wert 0 wird auch dann zurückgegeben, wenn der angegebene Stream über keinen Puffer verfügt oder nur zum Lesen geöffnet wird. Der Rückgabewert `EOF` gibt einen Fehler an.  
  
> [!NOTE]
>  Wenn `fflush` `EOF` zurückgibt, sind möglicherweise Daten aufgrund eines Schreibfehlers verloren gegangen. Bei der Einrichtung eines wichtigen Fehlerhandlers ist es am sichersten, die Pufferung mit der Funktion `setvbuf` zu deaktivieren oder eine E/A-Routine auf niedriger Ebene wie `_open`, `_close`, und `_write` anstelle der E/A-Streamfunktionen zu verwenden.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `fflush` leert den Stream `stream`. Wenn der Stream im Schreibmodus oder im Updatemodus geöffnet wurde und der letzte Vorgang ein Schreibvorgang war, werden die Inhalte des Streampuffers in die zugrunde liegende Datei bzw. das Gerät geschrieben, und der Puffer wird verworfen. Wenn der Stream im Lesemodus geöffnet wurde oder keinen Puffer besitzt, hat der Aufruf von `fflush` keine Auswirkungen, und der Puffer wird beibehalten. Ein Aufruf von `fflush` negiert die Wirkung aller vorherigen Aufrufe von `ungetc` für den Stream. Der Stream bleibt nach dem Aufruf geöffnet.  
  
 Wenn `stream` `NULL` ist, entspricht das Verhalten einem Aufruf von `fflush` in allen geöffneten Streams. Alle im Schreibmodus geöffneten Streams und alle Streams im Updatemodus, in denen der letzte Vorgang ein Schreibvorgang war, werden geleert. Der Aufruf hat keine Auswirkungen auf andere Streams.  
  
 Puffer werden normalerweise vom Betriebssystem verwaltet, das den optimalen Zeitpunkt bestimmt, zu dem Daten automatisch auf den Datenträger geschrieben werden: wenn ein Puffer voll ist, wenn ein Stream geschlossen wird oder wenn ein Programm normal beendet wird, ohne den Stream zu schließen. Mit der Datenträgercommitfunktion der Laufzeitbibliothek können Sie sicherstellen, dass wichtige Daten direkt auf den Datenträger anstatt in die Betriebssystempuffer geschrieben werden. Sie können diese Funktion aktivieren, ohne ein vorhandenes Programm umzuschreiben. Verknüpfen Sie hierzu die Objektdateien des Programms mit COMMODE.OBJ. In der resultierenden ausführbaren Datei schreiben Aufrufe von `_flushall` den Inhalt aller Puffer auf den Datenträger. COMMODE.OBJ hat nur Auswirkungen auf `_flushall` und `fflush`.  
  
 Weitere Informationen zum Steuern der Datenträgercommitfunktion finden Sie unter [Stream-E/A](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) und [_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
 Diese Funktion sperrt den aufrufenden Thread und ist threadsicher. Eine nicht sperrende Version finden Sie unter `_fflush_nolock`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fflush`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
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
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)