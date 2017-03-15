---
title: "fgets, fgetws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fgets"
  - "fgetws"
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
  - "_fgetts"
  - "fgetws"
  - "fgets"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fgetts-Funktion"
  - "fgets-Funktion"
  - "fgetts-Funktion"
  - "fgetws-Funktion"
  - "Streams, Abrufen von Zeichenfolgen aus"
  - "Streams, Lesen aus"
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# fgets, fgetws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rufen Sie eine Zeichenfolge aus einem Stream ab.  
  
## Syntax  
  
```  
char *fgets(   
   char *str,  
   int n,  
   FILE *stream   
);  
wchar_t *fgetws(   
   wchar_t *str,  
   int n,  
   FILE *stream   
);  
```  
  
#### Parameter  
 `str`  
 Speicherort für Daten.  
  
 `n`  
 Maximale Anzahl zu lesenden Zeichen.  
  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 Jede dieser Funktion gibt `str` zurück.  `NULL` zurückgegeben wird, um einen Fehler oder eine Dateiende\-Bedingung anzugeben.  Verwenden Sie `feof` oder `ferror`, um zu bestimmen, ob ein Fehler aufgetreten ist.  Wenn `str` oder `stream` ein NULL\-Zeiger ist oder `n` kleiner oder gleich null ist, Aufrufe dieser Funktion Parameterhandler der ungültige, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `fgets`\-Funktion liest eine Zeichenfolge vom Argument Eingabe `stream` und speichert sie in `str`.  `fgets` liest Zeichen von der aktuellen Streamposition an und das erste Zeilenumbruchzeichen, am Ende des Streams oder bis die Anzahl der Zeichenlesens einzuschließen entspricht `n` \- 1, das zuerst stammt.  Das Ergebnis, das im `str` gespeichert wird, wird mit einem NULL\-Zeichen angefügt.  Das Zeilenumbruchzeichen, wenn gelesen wird, wird in der Zeichenfolge enthalten.  
  
 `fgetws` ist eine Breitzeichenversion von `fgets`.  
  
 `fgetws` liest die `str` als Breitzeichenargument Mehrbyte\-Zeichenfolge oder Zeichenfolge mit Breitzeichen, ob `stream` im Textmodus oder im Binärdateimodus geöffnet ist, bzw.  Weitere Informationen zur Anwendung von Text\- und Binärmodi in Unicode\- und Multibyte\-Stream\-E\/A finden Sie unter [Text\- und Binärmodus\-Datei\-E\/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicode\-Stream\-E\/A in Text\- und Binärmodi](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_fgetts`|`fgets`|`fgets`|`fgetws`|  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fgets`|\<stdio.h\>|  
|`fgetws`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fgets.c  
// This program uses fgets to display  
// a line from a file on the screen.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[100];  
  
   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )  
   {  
      if( fgets( line, 100, stream ) == NULL)  
         printf( "fgets error\n" );  
      else  
         printf( "%s", line);  
      fclose( stream );  
   }  
}  
```  
  
## Eingabe: crt\_fgets.txt  
  
```  
Line one.  
Line two.  
```  
  
### Ausgabe  
  
```  
Line one.  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx)  
  
-   [System::IO::TextReader::ReadBlock](https://msdn.microsoft.com/en-us/library/system.io.textreader.readblock.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [puts, \_putws](../../c-runtime-library/reference/puts-putws.md)