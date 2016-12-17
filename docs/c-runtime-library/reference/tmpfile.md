---
title: "tmpfile"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "tmpfile"
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
  - "tmpfile"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Temporäre Dateien"
  - "tmpfile-Funktion"
  - "Temporäre Dateien, Erstellen"
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# tmpfile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine temporäre Datei.  Diese Funktion ist veraltet, da eine sicherere Version verfügbar ist; finden Sie unter [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md).  
  
## Syntax  
  
```  
FILE *tmpfile( void );  
```  
  
## Rückgabewert  
 Wenn erfolgreich, gibt `tmpfile` ein Stream\-Zeiger zurück.  Andernfalls wird ein `NULL` Zeiger zurück.  
  
## Hinweise  
 Die `tmpfile`\-Funktion erstellt eine temporäre Datei und gibt einen Zeiger auf diesem Stream zurück.  Die temporäre Datei wird im Stammverzeichnis erstellt.  Um keine temporäre Datei in einem Verzeichnis als dem Stammverzeichnis zu erstellen, verwenden Sie [tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) oder [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) in Verbindung mit [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Wenn die Datei nicht geöffnet werden kann, gibt `tmpfile` einen `NULL` \- Zeiger zurück.  Diese temporäre Datei wird automatisch gelöscht, wenn die Datei wird geschlossen, wenn das Programm beendet wird normalerweise oder `_rmtmp` aufgerufen und wird, dass das aktuelle Arbeitsverzeichnis nicht ändert.  Die temporäre Datei ist im Modus `w+b` \(unärer Lese\-\/Schreibzugriff\) geöffnet.  
  
 Fehler kann, wenn Sie versuchen, mehr als TMP\_MAX auftreten \(siehe STDIO.H Aufrufe\) mit `tmpfile`.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`tmpfile`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
> [!NOTE]
>  Dieses Beispiel erfordert Administratorrechte für die Ausführung unter Windows Vista.  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
  **Temporäre Datei 1 erstellt wurde**  
**Temporäre Datei 2 erstellt wurde**  
**Temporäre Datei 3 erstellt wurde**  
**3 temporäre Dateien gelöscht**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)