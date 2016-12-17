---
title: "fflush"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "fflush"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "fflush"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fflush-Funktion"
  - "Leeren"
  - "Streams, Leeren"
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 18
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# fflush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Leert einen Stream.  
  
## Syntax  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 `fflush` gibt 0 zurück, wenn der Puffer erfolgreich geleert wurde.  Der Wert 0 wird auch zurückgegeben in Fällen, in denen der angegebene Stream keinen Puffer hat oder ist nur für Lesezwecke geöffnet.  Bei dem Rückgabewert `EOF` gibt einen Fehler an.  
  
> [!NOTE]
>  Wenn `fflush``EOF` zurückgibt, verloren gegangen Daten möglicherweise aufgrund eines schreibensfehlers.  Wenn Sie einen Handler des schwer wiegender Fehlers installiert, ist es am sichersten, weg puffern mit der Funktion `setvbuf` zu drehen oder auf niedriger Ebene wie `_open` zu verwenden E\/A\-Routinen, funktioniert `_close` und `_write` anstelle der Stream\-E\/A.  
  
## Hinweise  
 Die `fflush`\-Funktion leert einen Stream.  Wenn die Datei, die `stream` zugeordnet ist, für Ausgabezwecke geöffnet ist, wird `fflush` in der Datei der Inhalt des Puffers, der dem Stream zugeordnet ist.  Wenn der Stream für die Eingabe geöffnet ist, werden `fflush` den Inhalt aus dem Puffer.  `fflush` negiert die Auswirkung jedes früheren Aufrufs von `ungetc` für `stream`.  Auch `fflush(NULL)` löscht alle Streams, die für die Ausgabe geöffnet sind.  Der Stream bleibt nach dem Aufruf geöffnet.  `fflush` hat keine Auswirkungen auf einen nicht zwischengespeicherten Stream.  
  
 Puffer werden normalerweise vom Betriebssystem verwaltet, das die optimale Zeit bestimmt, die Daten auf dem Datenträger automatisch zu schreiben: wenn ein Puffer ist voll, wenn ein Stream geschlossen wird oder wenn ein Programm normalerweise wird beendet, ohne den Stream zu schließen.  Die Datenträgercommitfunktion der Laufzeitbibliothek können Sie sicherstellen, dass wichtige Daten direkt auf dem Datenträger statt zu den Betriebssystempuffern geschrieben werden.  Ohne ein vorhandenes Programm umzuschreiben, können Sie diese Funktion aktivieren, indem Sie die Objektdateien des Programms mit COMMODE.OBJ verknüpfen.  In der resultierenden ausführbaren Datei schreiben Aufrufe von `_flushall` den Inhalt aller Puffer auf den Datenträger.  Nur `_flushall` und `fflush` werden von COMMODE.OBJ beeinflusst.  
  
 Weitere Informationen zum Steuern der Datenträgercommitfunktion finden Sie unter [Stream\-E\/A](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) und [\_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
 Diese Funktion sperrt den aufrufenden Thread und daher threadsicher.  Eine nicht sperrende Version finden Sie unter `_fflush_nolock`.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fflush`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
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
  
  **`Dies ist ein Test Dies ist testThis`  `ist ein Test Dies ist ein testEnter` ein Satz von vier Wörtern mit scanf: Dies ist ein Test**  
**Dieses \-**  
**is**  
**a**  
**Testen**  
**Geben Sie denselben Satz mit abruft ein: Dies ist ein Test**  
**Dies ist ein Test**   
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)