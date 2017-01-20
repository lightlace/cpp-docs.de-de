---
title: "_read"
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
  - "_read"
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
  - "_read"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_read-Funktion"
  - "Daten [C++], Lesen"
  - "Daten [CRT]"
  - "Dateien [C++], Lesen"
  - "read-Funktion"
  - "Lesen von Daten [C++]"
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _read
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest Daten aus einer Datei.  
  
## Syntax  
  
```  
  
      int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor, der die geöffnete Datei verweist.  
  
 *buffer*  
 Speicherort für Daten.  
  
 *count*  
 Maximale Anzahl Bytes.  
  
## Rückgabewert  
 \_**Lesen** gibt die Anzahl der gelesenen Bytes zurück, die möglicherweise kleiner als *zählen* ist, wenn weniger als *die Zählbytes* gibt, die in der Datei verbleiben, oder wenn die Datei im Textmodus geöffnet war, in diesem Fall jedes Paar des Wagenrücklauf\-Zeilenvorschubs \(CR\-LF\) durch ein einzelnes Zeilenvorschubzeichen ersetzt wird.  Nur das einzelne Zeilenvorschubzeichen wird im Rückgabewert gezählt.  Die Ersetzung nicht beeinflusst der Dateizeiger.  
  
 Wenn versucht, die Funktion am Dateiende gelesen, gibt sie 0 zurück.  Wenn `fd` NULL ist, ist die Datei nicht zum Lesen geöffnet, oder die Datei wird, der ungültige Parameterhandler gesperrt wird aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, kehrt die Feature \- 1 zurück und legt `errno` auf `EBADF` fest.  
  
 Wenn *Puffer***NULL**, wird der ungültige Parameterhandler aufgerufen.  Wenn die Ausführung zulässig ist, um fortzufahren, gibt die Funktion \-1 zurück und `errno` ist auf `EINVAL` festgelegt.  
  
 Weitere Informationen über diese und andere Rückgabecodes, finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_read`\-Funktion liest maximal in *Zählbytes* *Puffer* aus der Datei, die `fd` zugeordnet ist.  Der Lesevorgang beginnt in der aktuellen Position des Dateizeigers, der der angegebenen Datei zugeordnet ist.  Nach den Lesevorgang zeigt der Dateizeiger beim folgenden ungelesenen Zeichen.  
  
 Wenn die Datei im Textmodus geöffnet war, wird das Lesen, wenn `_read` ein STRG\+Z\-Zeichen trifft, das als Dateiende\-Indikator behandelt wird.  Verwenden Sie [\_lseek](../../c-runtime-library/reference/lseek-lseeki64.md), den Dateiende\-Indikator zu löschen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_read`|\<io.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
## Eingabe: crt\_read.txt  
  
```  
Line one.  
Line two.  
```  
  
## Ausgabe  
  
```  
Read 19 bytes from file  
```  
  
## Siehe auch  
 [E\/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_write](../../c-runtime-library/reference/write.md)