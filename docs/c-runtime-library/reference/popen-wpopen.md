---
title: "_popen, _wpopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_popen"
  - "_wpopen"
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
  - "tpopen"
  - "popen"
  - "wpopen"
  - "_popen"
  - "_wpopen"
  - "_tpopen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_popen-Funktion"
  - "_tpopen-Funktion"
  - "_wpopen-Funktion"
  - "Pipes, Erstellen"
  - "popen-Funktion"
  - "tpopen-Funktion"
  - "wpopen-Funktion"
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _popen, _wpopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Pipe und führt einen Befehl aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
  
      FILE *_popen(  
const char *command,  
const char *mode   
);  
FILE *_wpopen(  
const wchar_t *command,  
const wchar_t *mode   
);  
```  
  
#### Parameter  
 *command*  
 Befehl, der ausgeführt werden soll.  
  
 *mode*  
 Modus des zurückgegebenen Streams.  
  
## Rückgabewert  
 Gibt einen Stream zurück, der einem Ende der erstellten Pipe zugeordnet ist.  Das andere Ende der Pipe ist der Standardeingabe oder Standardausgabe des erzeugten Befehls zugeordnet.  Die Funktionen geben bei einem Fehler **NULL** zurück.  Wenn der Fehler ein ungültiger Parameter ist, etwa wenn *command* oder *mode* ein NULL\-Zeiger ist, oder *mode* kein gültiger Modus ist, wird `errno` auf `EINVAL` festgelegt.  Gültige Modi können Sie dem Abschnitt mit den Hinweisen entnehmen.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_popen`\-Funktion erstellt eine Pipe und führt asynchron eine generierte Kopie des Befehlsprozessors mit der angegebenen Zeichenfolge *command* aus.  Die Zeichenfolge *mode* gibt den angeforderten Zugriffstyp wie folgt an.  
  
 **"r"**  
 Der aufrufende Prozess kann die Standardausgabe des erzeugten Befehls mit dem zurückgegebenen Stream lesen.  
  
 **"w"**  
 Der aufrufende Prozess kann die Standardeingabe des erzeugten Befehls mit dem zurückgegebenen Stream schreiben.  
  
 **"b"**  
 Öffnen im binären Modus.  
  
 **"t"**  
 Öffnen im Textmodus.  
  
> [!NOTE]
>  Wenn die `_popen`\-Funktion in einem Windows\-Programm verwendet wird, gibt sie einen ungültigen Dateizeiger zurück, der dafür sorgt, dass das Programm für unbestimmte Zeit nicht mehr reagiert.  `_popen` funktioniert in einer Konsolenanwendung.  Wie eine Windows\-Anwendung erstellt wird, die Eingabe und Ausgabe umleitet, lesen Sie im Artikel zum [Erstellen eines untergeordneten Prozesses mit umgeleiteter Eingabe und Ausgabe](http://msdn.microsoft.com/library/windows/desktop/ms682499) von [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 `_wpopen` ist eine Breitzeichenversion von `_popen`. Das *path*\-Argument für `_wpopen` ist eine Breitzeichenfolge.  `_wpopen` und `_popen` verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tpopen`|`_popen`|`_popen`|`_wpopen`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_popen`|\<stdio.h\>|  
|`_wpopen`|\<stdio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_popen.c  
/* This program uses _popen and _pclose to receive a   
 * stream of text from a system process.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
  
   char   psBuffer[128];  
   FILE   *pPipe;  
  
        /* Run DIR so that it writes its output to a pipe. Open this  
         * pipe with read text attribute so that we can read it   
         * like a text file.   
         */  
  
   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )  
      exit( 1 );  
  
   /* Read pipe until end of file, or an error occurs. */  
  
   while(fgets(psBuffer, 128, pPipe))  
   {  
      printf(psBuffer);  
   }  
  
   /* Close pipe and print return value of pPipe. */  
   if (feof( pPipe))  
   {  
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );  
   }  
   else  
   {  
     printf( "Error: Failed to read the pipe to the end.\n");  
   }  
}  
```  
  
## Beispielausgabe  
 Bei dieser Ausgabe wird davon ausgegangen, dass das aktuelle Verzeichnis nur eine Datei mit der Dateinamenerweiterung .c enthält.  
  
```  
 Volume in drive C is CDRIVE  
 Volume Serial Number is 0E17-1702  
  
 Directory of D:\proj\console\test1  
  
07/17/98  07:26p                   780 popen.c  
               1 File(s)            780 bytes  
                             86,597,632 bytes free  
  
Process returned 0  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [\_pclose](../../c-runtime-library/reference/pclose.md)   
 [\_pipe](../../c-runtime-library/reference/pipe.md)