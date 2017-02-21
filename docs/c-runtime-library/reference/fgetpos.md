---
title: "fgetpos | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fgetpos"
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
  - "fgetpos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fgetpos-Funktion"
  - "Streams, Dateipositionsindikator"
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# fgetpos
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft Stellungsanzeiger eines Streams ab.  
  
## Syntax  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### Parameter  
 `stream`  
 Zielstream.  
  
 `pos`  
 Position\-Indikatorspeicher.  
  
## Rückgabewert  
 Wenn erfolgreich, `fgetpos` gibt 0 zurück.  Bei einem Fehler wird ein Wert ungleich 0 \(null\) zurück und legt `errno` auf eine der folgenden Manifestkonstanten fest \(in STDIO.H\): `EBADF`, der den jeweiligen Stream bedeutet, ist kein gültiger Dateizeiger oder ist nicht möglich oder `EINVAL` verwendet, der Folgendes bedeutet, dass der `stream`\-Wert oder der Wert von `pos` ungültig wird, beispielsweise, wenn entweder ein NULL\-Zeiger ist.  Wenn `stream` oder `pos` ein `NULL` Zeiger ist, ruft die Funktion den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
## Hinweise  
 Die Funktion ruft `fgetpos` den aktuellen Wert des `stream` Stellungsanzeigers Arguments ab und speichert ihn im Objekt, das auf den durch `pos` gezeigt wird.  Die `fsetpos`\-Funktion kann Informationen später verwenden, die in `pos` gespeichert werden, um den Zeiger des `stream`\-Arguments an seiner Position zurückzusetzen, wenn `fgetpos` aufgerufen wurde.  Der Wert `pos` wird in einem internen Format gespeichert und ist nur über `fgetpos` und `fsetpos` bestimmt.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fgetpos`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## Eingabe: crt\_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### Ausgabe crt\_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../../c-runtime-library/reference/fsetpos.md)