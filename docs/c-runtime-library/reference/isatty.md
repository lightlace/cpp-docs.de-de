---
title: "isatty | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isatty"
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
  - "isatty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "isatty-Funktion"
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _isatty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein Dateideskriptor einem Zeichengerät zugeordnet ist.  
  
## Syntax  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor, der auf das zu testende Gerät verweist.  
  
## Rückgabewert  
 `_isatty` gibt einen Wert ungleich 0 \(null\) zurück, wenn ein Deskriptor einem Zeichengerät zugeordnet ist.  Andernfalls gibt `_isatty` 0 zurück.  
  
## Hinweise  
 Die `_isatty`\-Funktion bestimmt, ob `fd` einem Zeichengerät zugeordnet ist \(Terminal, Konsole, Drucker oder serieller Anschluss\).  
  
 Diese Funktion überprüft den `fd`\-Parameter.  Wenn `fd` ein ungültiger Dateizeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion 0 zurück und stellt `errno` auf `EBADF` ein.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_isatty`|\<io.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## Beispielausgabe  
  
```  
stdout has not been redirected to a file  
```  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)