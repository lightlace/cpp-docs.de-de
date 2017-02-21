---
title: "_chdir, _wchdir | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wchdir"
  - "_chdir"
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
  - "tchdir"
  - "_chdir"
  - "_wchdir"
  - "_tchdir"
  - "wchdir"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tchdir-Funktion"
  - "_chdir-Funktion"
  - "_wchdir-Funktion"
  - "tchdir-Funktion"
  - "wchdir-Funktion"
  - "chdir-Funktion"
  - "Verzeichnisse [C++], ändern"
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _chdir, _wchdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert das aktuelle Arbeitsverzeichnis.  
  
## Syntax  
  
```  
int _chdir(   
   const char *dirname   
);  
int _wchdir(   
   const wchar_t *dirname   
);  
```  
  
#### Parameter  
 `dirname`  
 Pfad des neuen Arbeitsverzeichnisses.  
  
## Rückgabewert  
 Diese Funktionen geben bei Erfolg den Wert 0 zurück. Ein Rückgabewert von 1 gibt einen Fehler an. Wenn der angegebene Pfad nicht gefunden werden kann, wird `errno`  auf `ENOENT` festgelegt. Wenn `dirname` NULL ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno`  auf `EINVAL`  gesetzt, und die Funktion gibt – 1 zurück.  
  
## Hinweise  
 Die `_chdir` \-Funktion ändert das aktuelle Arbeitsverzeichnis und wählt das Verzeichnis aus, das durch `dirname` angegeben ist. Der `dirname`\-Parameter muss auf ein vorhandenes Verzeichnis verweisen. Diese Funktion kann das aktuelle Arbeitsverzeichnis auf jedem beliebigen Laufwerk ändern. Wenn ein neuer Laufwerkbuchstabe in `dirname` angegeben wird, wird der Standardlaufwerkbuchstabe ebenfalls geändert. Wenn z. B. A der Standardlaufwerkbuchstabe und \\BIN das aktuelle Arbeitsverzeichnis ist, ändert der folgende Aufruf das aktuelle Arbeitsverzeichnis in C und legt C als neues Standardlaufwerk fest:  
  
```  
_chdir("c:\\temp");  
```  
  
 Wenn Sie den optionalen umgekehrten Schrägstrich \(`\`\) in Pfadangaben verwenden, müssen Sie in einem C\-Zeichenfolgenliteral zwei umgekehrte Schrägstriche \(`\\`\) platzieren, um einen einzelnen umgekehrten Schrägstrich \(`\`\) darzustellen.  
  
 `_wchdir` ist eine Breitzeichenversion von `_chdir`. Das `dirname`\-Argument für `_wchdir` ist eine Zeichenfolge mit Breitzeichen`. _wchdir` und `_chdir` verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen:  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tchdir`|`_chdir`|`_chdir`|`_wchdir`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_chdir`|\<direct.h\>|\<errno.h\>|  
|`_wchdir`|\<direct.h\> oder \<wchar.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_chdir.c  
// arguments: C:\WINDOWS  
  
/* This program uses the _chdir function to verify  
   that a given directory exists. */  
  
#include <direct.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( int argc, char *argv[] )  
{  
  
   if(_chdir( argv[1] ) )  
   {  
      switch (errno)  
      {  
      case ENOENT:  
         printf( "Unable to locate the directory: %s\n", argv[1] );  
         break;  
      case EINVAL:  
         printf( "Invalid buffer.\n");  
         break;  
      default:  
         printf( "Unknown error.\n");  
      }  
   }  
   else  
      system( "dir *.exe");  
}  
```  
  
```Output  
Volume in Laufwerk C hat keine Bezeichnung. Volumeseriennummer ist 2018-08A1 Verzeichnis von C:\Windows 29.08.2002  04:00         1.004.032 explorer.exe 17.12.2002  16:43            10.752 hh.exe 03.03.2003  09:24            33.792 ieuninst.exe 29.10.1998  16:45           306.688 IsUninst.exe 29.08.2002  04:00            66.048 NOTEPAD.EXE 03.03.2003  09:24            33.792 Q330994.exe 29.08.2002  04:00           134.144 regedit.exe 28.02.2003  18:26            46.352 setdebug.exe 29.08.2002  04:00            15.360 TASKMAN.EXE 29.08.2002  04:00            49.680 twunk_16.exe 29.08.2002  04:00            25.600 twunk_32.exe 29.08.2002  04:00           256.192 winhelp.exe 29.08.2002  04:00           266.752 winhlp32.exe 13 Datei(en)      2.249.184 Bytes 0 Verzeichnis(se)  67.326.029.824 Bytes frei  
```  
  
## .NET Framework-Entsprechung  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)