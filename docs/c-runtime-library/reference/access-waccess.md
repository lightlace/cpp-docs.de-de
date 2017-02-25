---
title: "_access, _waccess | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_access"
  - "_waccess"
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
  - "_waccess"
  - "_access"
  - "taccess"
  - "waccess"
  - "_taccess"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_access-Funktion"
  - "_taccess-Funktion"
  - "_waccess-Funktion"
  - "access-Funktion"
  - "taccess-Funktion"
  - "waccess-Funktion"
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _access, _waccess
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob eine Datei schreibgeschützt ist oder nicht.  Sicherere Versionen verfügbar sind; finden Sie unter [\_access\_s, \_waccess\_s](../../c-runtime-library/reference/access-s-waccess-s.md).  
  
## Syntax  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### Parameter  
 `path`  
 Datei oder Verzeichnispfad.  
  
 `mode`  
 Lese\-Schreibattribut.  
  
## Rückgabewert  
 Jede Funktion gibt 0 zurück, wenn die Datei den angegebenen Modus hat.  Die Funktion gibt \- 1, wenn für die benannte Datei nicht vorhanden zurück oder verfügt nicht den angegebenen Modus; in diesem Fall wird `errno` wie in der folgenden Tabelle festgelegt.  
  
 `EACCES`  
 Zugriff verweigert: die Berechtigungseinstellung der Datei kann nicht angegebenen Zugriff.  
  
 `ENOENT`  
 Dateiname oder Pfad nicht gefunden.  
  
 `EINVAL`  
 Ungültiger Parameter.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Wenn sie mit Dateien verwendet wird, bestimmt die `_access`\-Funktion, ob die angegebene Datei oder das Verzeichnis vorhanden und besitzt die Attribute, die durch den Wert von `mode` angegeben werden.  Wenn es mit Verzeichnissen verwendet wird, bestimmt das `_access` nur, ob das angegebene Verzeichnis vorhanden; in [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] und in den neueren Betriebssystemen haben alle Verzeichnisse der Lese\- und Schreibzugriff.  
  
|`mode`\-Wert|Überprüfungen für Datei|  
|------------------|-----------------------------|  
|00|Nur Vorhandensein|  
|02|Nur Schreibzugriff|  
|04|Schreibgeschützt|  
|06|Lesen und Schreiben Sie|  
  
 Diese Funktion liest nur, ob die Datei und das Verzeichnis oder nicht schreibgeschützt sind, es überprüft nicht die Dateisystemsicherheitseinstellungen.  Für das benötigen Sie ein Zugriffstoken.  Weitere Informationen über Dateisystemsicherheit, finden Sie unter [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909).  Eine ATL\-Klasse vorhanden ist, um diese Funktion bereitzustellen; finden Sie unter [CAccessToken Class](../../atl/reference/caccesstoken-class.md).  
  
 `_waccess` ist eine Breitzeichenversion von `_access`. Das `path`\-Argument für `_waccess` ist eine Breitzeichenfolge.  `_waccess` und `_access` verhalten sich andernfalls identisch.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `path``NULL` ist, oder `mode` kein gültiger Modus angibt, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, legt die Funktion `errno` auf `EINVAL` fest und gibt \-1 zurück.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`_access`|\<io.h\>|\<errno.h\>|  
|`_waccess`|\<wchar.h oder\> io.h \<\>|\<errno.h\>|  
  
## Beispiel  
 Im folgenden Beispiel wird `_access` verwendet, um die Datei zu überprüfen, die crt\_ACCESS.C, um festzustellen genannt wird, ob sie vorhanden ist und dass das Schreiben zulässt wird.  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
  **Datei crt\_ACCESS.C vorhanden ist.**  
**Datei crt\_ACCESS.C ist kein Schreibzugriff möglich.**   
## .NET Framework-Entsprechung  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat\- und \_wstat\-Funktionen](../../c-runtime-library/reference/stat-functions.md)