---
title: "tmpfile_s"
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
  - "tmpfile_s"
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
  - "tmpfile_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Temporäre Dateien"
  - "tmpfile_s-Funktion"
  - "Temporäre Dateien, Erstellen"
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: 20
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# tmpfile_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine temporäre Datei.  Es ist eine Version von [tmpfile](../../c-runtime-library/reference/tmpfile.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### Parameter  
 \[out\] `pFilePtr`  
 Die Adresse eines Zeigers, um die Adresse des generierten Zeigers in einen Stream zu speichern.  
  
## Rückgabewert  
 Gibt bei Erfolg 0 \(null\) zurück und einen Fehlercode, wenn ein Fehler auftritt.  
  
### Fehlerbedingungen  
  
|`pFilePtr`|**Rückgabewert**|**Contents of**  `pFilePtr`|  
|----------------|----------------------|---------------------------------|  
|`NULL`|`EINVAL`|nicht geändert|  
  
 Wenn der obige Parametervalidierungsfehler auftritt, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno` auf `EINVAL` festgelegt und der Rückgabewert ist `EINVAL`.  
  
## Hinweise  
 Die `tmpfile_s`\-Funktion erstellt eine temporäre Datei und fügt einen Zeiger auf diesem Stream in das `pFilePtr` ein Argument.  Die temporäre Datei wird im Stammverzeichnis erstellt.  Um keine temporäre Datei in einem Verzeichnis als dem Stammverzeichnis zu erstellen, verwenden Sie [tmpnam\_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) oder [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) in Verbindung mit [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Wenn die Datei nicht geöffnet werden kann, wird `tmpfile_s` von `NULL` in `pFilePtr`\-Parameter.  Diese temporäre Datei wird automatisch gelöscht, wenn die Datei wird geschlossen, wenn das Programm beendet wird normalerweise oder `_rmtmp` aufgerufen und wird, dass das aktuelle Arbeitsverzeichnis nicht ändert.  Die temporäre Datei ist im Modus `w+b` \(unärer Lese\-\/Schreibzugriff\) geöffnet.  
  
 Fehler kann, wenn Sie versuchen, mehr als `TMP_MAX_S` vorkommen \(siehe STDIO.H\) Aufrufe mit `tmpfile_s.`  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`tmpfile_s`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
> [!NOTE]
>  Dieses Beispiel erfordert Administratorrechte für die Ausführung unter Windows Vista.  
  
```  
// crt_tmpfile_s.c  
// This program uses tmpfile_s to create a  
// temporary file, then deletes this file with _rmtmp.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char tempstring[] = "String to be written";  
   int  i;  
   errno_t err;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      err = tmpfile_s(&stream);  
      if( err )  
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