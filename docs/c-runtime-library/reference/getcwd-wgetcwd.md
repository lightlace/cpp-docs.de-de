---
title: "_getcwd, _wgetcwd"
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
  - "_wgetcwd"
  - "_getcwd"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getcwd"
  - "wgetcwd"
  - "_wgetcwd"
  - "tgetcwd"
  - "_tgetcwd"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "getcwd-Funktion"
  - "Arbeitsverzeichnis"
  - "_wgetcwd-Funktion"
  - "_getcwd-Funktion"
  - "Aktuelles Arbeitsverzeichnis"
  - "wgetcwd-Funktion"
  - "Verzeichnisse [C++], aktuelle Arbeit"
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# _getcwd, _wgetcwd
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft das aktuelle Arbeitsverzeichnis ab.  
  
## Syntax  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für den Pfad.  
  
 `maxlen`  
 Maximale Länge des Pfads in Zeichen: `char` für `_getcwd` und `wchar_t` für `_wgetcwd`.  
  
## Rückgabewert  
 Gibt einen Zeiger auf `buffer` zurück. Ein `NULL`\-Rückgabewert zeigt einen Fehler an, und `errno` wird entweder auf `ENOMEM` festgelegt, um anzugeben, dass nicht genügend Arbeitsspeicher zum Zuordnen von `maxlen` Bytes vorhanden ist \(wenn ein `NULL`\-Argument als `buffer` angegeben wird\), oder auf `ERANGE`, um anzugeben, dass der Pfad länger als `maxlen` Zeichen ist. Wenn `maxlen` kleiner oder gleich Null ist, ruft diese Funktion einen Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_getcwd`\-Funktion ruft für das Standardlaufwerk den vollständigen Pfad des aktuellen Arbeitsverzeichnis ab und speichert ihn unter `buffer`. Das ganzzahlige Argument `maxlen` gibt die maximale Länge für den Pfad an. Ein Fehler tritt auf, wenn die Länge des Pfads \(einschließlich des abschließenden NULL\-Zeichens\) `maxlen` überschreitet*.* Das `buffer`\-Argument kann `NULL` sein. Es wird dann automatisch ein Puffer mit einer Mindestgröße von `maxlen` \(mehr nur bei Bedarf\) zugeordnet und `malloc` zum Speichern des Pfades verwendet. Dieser Puffer kann später geleert werden, indem `free` aufgerufen und der `_getcwd`\-Rückgabewert \(ein Zeiger auf den zugeordneten Puffer\) übergeben werden.  
  
 `_getcwd`gibt eine Zeichenfolge zurück, die den Pfad des aktuellen Arbeitsverzeichnisses repräsentiert. Wenn das aktuelle Arbeitsverzeichnis das Stammverzeichnis ist, endet die Zeichenfolge mit einem umgekehrten Schrägstrich \(`\`\). Wenn das aktuelle Arbeitsverzeichnis nicht das Stammverzeichnis ist, endet die Zeichenfolge mit dem Verzeichnisnamen und nicht mit einem umgekehrten Schrägstrich.  
  
 `_wgetcwd` ist eine Breitzeichenversion von `_getcwd`. Das Argument `buffer` und der Rückgabewert von `_wgetcwd` sind Zeichenfolgen mit Breitzeichen.`_wgetcwd` und `_getcwd` verhalten sich andernfalls identisch.  
  
 Wenn `_DEBUG` und `_CRTDBG_MAP_ALLOC` definiert sind, werden Aufrufe von `_getcwd` und `_wgetcwd` durch Aufrufe von `_getcwd_dbg` und `_wgetcwd_dbg` ersetzt, um das Debuggen von Speicherbelegungen zuzulassen. Weitere Informationen finden Sie unter [\_getcwd\_dbg, \_wgetcwd\_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_getcwd`|\<direct.h\>|  
|`_wgetcwd`|\<direct.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## .NET Framework-Entsprechung  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)