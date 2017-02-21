---
title: "_chmod, _wchmod | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chmod"
  - "_wchmod"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_chmod"
  - "_wchmod"
  - "wchmod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chmod-Funktion"
  - "_wchmod-Funktion"
  - "chmod-Funktion"
  - "Dateiberechtigungen [C++]"
  - "Dateien [C++], Ändern von Berechtigungen"
  - "wchmod-Funktion"
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _chmod, _wchmod
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die DateiBerechtigungseinstellungen.  
  
## Syntax  
  
```  
  
      int _chmod(   
   const char *filename,  
   int pmode   
);  
int _wchmod(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### Parameter  
 `filename`  
 Name der vorhandenen Datei.  
  
 `pmode`  
 Berechtigungseinstellung für die Datei.  
  
## Rückgabewert  
 Diese Funktionen geben 0 zurück, wenn die Berechtigungseinstellung erfolgreich geändert wird.  Ein Rückgabewert von 1 gibt einen Fehler an.  Wenn die angegebene Datei nicht gefunden werden konnte, wird `errno` auf `ENOENT` festgelegt; Wenn ein Parameter nicht gültig ist, wird `errno` auf `EINVAL` festgelegt.  
  
## Hinweise  
 Die `_chmod`, welche Funktion änder die Berechtigungseinstellung der Datei durch `filename` angegeben *.* Die Berechtigungseinstellung steuert den Lese\- und Schreibzugriff auf die Datei.  Der ganzzahlige Ausdruck `pmode` enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\\Stat.h.  
  
 `_S_IWRITE`  
 Schreiben zulässig.  
  
 `_S_IREAD`  
 Lesen zulässig.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben zulässig.  
  
 Wenn beide Konstanten angegeben werden, sind sie mit dem bitweisen Operator `OR` verknüpft \(          `|` \).  Wenn Schreibberechtigung nicht angegeben wird, ist die Datei schreibgeschützt.  Beachten Sie, dass alle Dateien immer Lesbarkeit sind; es ist nicht möglich, lesegeschützte Berechtigung zu geben.  Daher spielt die Modi `_S_IWRITE` und `_S_IREAD | _S_IWRITE`.  
  
 `_wchmod` ist eine Breitzeichenversion von `_chmod`. Das `filename`\-Argument für `_wchmod` ist eine Breitzeichenfolge.  `_wchmod` und `_chmod` verhalten sich andernfalls identisch.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `pmode` keine Kombination einer Manifestkonstanten ist oder einen alternative Konstanten enthält, ignoriert die Funktion einfach die.  Wenn `filename` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno` auf `EINVAL` und Funktionsrückgaben \-1 festgelegt.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_chmod`|\<io.h\>|\<sys\/types.h, sys\>\<\/stat.h, errno.h\>\<\>|  
|`_wchmod`|\<io.h oder\> wchar.h \<\>|\<sys\/types.h, sys\>\<\/stat.h, errno.h\>\<\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_chmod.c  
// This program uses _chmod to  
// change the mode of a file to read-only.  
// It then attempts to modify the file.  
//  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
// Change the mode and report error or success   
void set_mode_and_report(char * filename, int mask)  
{  
   // Check for failure   
   if( _chmod( filename, mask ) == -1 )  
   {  
      // Determine cause of failure and report.   
      switch (errno)  
      {  
         case EINVAL:  
            fprintf( stderr, "Invalid parameter to chmod.\n");  
            break;  
         case ENOENT:  
            fprintf( stderr, "File %s not found\n", filename );  
            break;  
         default:  
            // Should never be reached   
            fprintf( stderr, "Unexpected error in chmod.\n" );  
       }  
   }  
   else  
   {  
      if (mask == _S_IREAD)  
        printf( "Mode set to read-only\n" );  
      else if (mask & _S_IWRITE)  
        printf( "Mode set to read/write\n" );  
   }  
   fflush(stderr);  
}  
  
int main( void )  
{   
  
   // Create or append to a file.   
   system( "echo /* End of file */ >> crt_chmod.c_input" );  
  
   // Set file mode to read-only:   
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );  
  
   // Change back to read/write:   
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );   
}   
```  
  
  **`Eine Textzeile.`  `Eine Textzeile.`  Modus festgelegt auf schreibgeschützt**  
**Der Zugriff wird verweigert.**  
**Modus festgelegt auf Lese\-\/Schreibzugriff**   
## .NET Framework-Entsprechung  
  
-   [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
-   [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat\- und \_wstat\-Funktionen](../../c-runtime-library/reference/stat-functions.md)