---
title: "_mkdir, _wmkdir | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmkdir"
  - "_mkdir"
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
  - "_mkdir"
  - "tmkdir"
  - "_tmkdir"
  - "wmkdir"
  - "_wmkdir"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mkdir-Funktion"
  - "_tmkdir-Funktion"
  - "_wmkdir-Funktion"
  - "Verzeichnisse [C++], Erstellen"
  - "Ordner [C++], Erstellen"
  - "mkdir-Funktion"
  - "tmkdir-Funktion"
  - "wmkdir-Funktion"
ms.assetid: 7f22d01d-63a5-4712-a6e7-d34878b2d840
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mkdir, _wmkdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt ein neues Verzeichnis.  
  
## Syntax  
  
```  
  
      int _mkdir(  
   const char *dirname   
);  
int _wmkdir(  
   const wchar_t *dirname   
);  
```  
  
#### Parameter  
 `dirname`  
 Pfad für ein neues Verzeichnis.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt den Wert 0 zurück, wenn das neue Verzeichnis erstellt wurde.  Bei einem Fehler wird die Funktion \- 1 zurück und legt `errno` wie folgt fest.  
  
 `EEXIST`  
 Verzeichnis wurde nicht erstellt, da `dirname` der Name einer vorhandenen Datei, des Verzeichnisses oder des Geräts ist.  
  
 `ENOENT`  
 Pfad wurde nicht gefunden.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_mkdir`\-Funktion erstellt ein neues Verzeichnis mit dem angegebenen *dirname.* `_mkdir` kann nur ein neues Verzeichnis pro Aufruf erstellen, sodass nur die letzte Komponente von `dirname` können Sie ein neues Verzeichnis benennen.  `_mkdir` übersetzt nicht Pfadtrennzeichen.  In Windows NT sind der umgekehrte Schrägstrich \(\\\) und der Schrägstrich \(\/\) gültige Pfadtrennzeichen in Zeichenfolgen in den Ablaufroutinen.  
  
 `_wmkdir` ist eine Breitzeichenversion von `_mkdir`. Das `dirname`\-Argument für `_wmkdir` ist eine Breitzeichenfolge.  `_wmkdir` und `_mkdir` verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tmkdir`|`_mkdir`|`_mkdir`|`_wmkdir`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mkdir`|\<direct.h\>|  
|`_wmkdir`|\<direct.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_makedir.c  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   if( _mkdir( "\\testtmp" ) == 0 )  
   {  
      printf( "Directory '\\testtmp' was successfully created\n" );  
      system( "dir \\testtmp" );  
      if( _rmdir( "\\testtmp" ) == 0 )  
        printf( "Directory '\\testtmp' was successfully removed\n"  );  
      else  
         printf( "Problem removing directory '\\testtmp'\n" );  
   }  
   else  
      printf( "Problem creating directory '\\testtmp'\n" );  
}  
```  
  
## Beispielausgabe  
  
```  
Directory '\testtmp' was successfully created  
 Volume in drive C has no label.  
 Volume Serial Number is E078-087A  
  
 Directory of C:\testtmp  
  
02/12/2002  09:56a      <DIR>          .  
02/12/2002  09:56a      <DIR>          ..  
               0 File(s)              0 bytes  
               2 Dir(s)  15,498,690,560 bytes free  
Directory '\testtmp' was successfully removed  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx)  
  
-   [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)  
  
## Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)