---
title: "_access_s, _waccess_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_access_s"
  - "_waccess_s"
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
  - "waccess_s"
  - "access_s"
  - "_waccess_s"
  - "_access_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_access_s-Funktion"
  - "_taccess_s-Funktion"
  - "_waccess_s-Funktion"
  - "access_s-Funktion"
  - "taccess_s-Funktion"
  - "waccess_s-Funktion"
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _access_s, _waccess_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt Dateilese\-\/schreibberechtigung.  Dies ist eine Version von [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### Parameter  
 `path`  
 Datei oder Verzeichnispfad.  
  
 `mode`  
 Berechtigungseinstellung.  
  
## Rückgabewert  
 Jede Funktion gibt 0 zurück, wenn die Datei den angegebenen Modus hat.  Die Funktion gibt ein Fehlercode, wenn für die benannte Datei nicht vorhanden ist oder nicht wieder im angegebenen Modus zugreifen.  In diesem Fall gibt die Funktion ein Fehlercode wie folgt aus dem Satz zurück und legt auch `errno` auf den gleichen Wert fest.  
  
 `EACCES`  
 Zugriff verweigert.  Die Berechtigungseinstellung der Datei kann nicht angegebenen Zugriff.  
  
 `ENOENT`  
 Dateiname oder Pfad nicht gefunden.  
  
 `EINVAL`  
 Ungültiger Parameter.  
  
 Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Wenn sie mit Dateien verwendet wird, bestimmt die `_access_s`\-Funktion, ob auf die angegebene Datei vorhanden und zugegriffen werden kann, wie durch den Wert von `mode` angegeben.  Wenn es mit Verzeichnissen verwendet wird, bestimmt das `_access_s` nur, ob das angegebene Verzeichnis vorhanden ist.  In [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] und in neueren Betriebssystemen haben alle Verzeichnisse der Lese\- und Schreibzugriff.  
  
|Moduswert|Überprüfungen für Datei|  
|---------------|-----------------------------|  
|00|Nur Vorhandensein.|  
|02|Schreibberechtigungen.|  
|04|Berechtigung.|  
|06|Lese\- Schreibberechtigungen.|  
  
 Berechtigung, die Datei zu lesen oder zu schreiben ist, nicht ausreichend, um die Möglichkeit sicherzustellen, eine Datei zu öffnen.  Wenn eine Datei von einem anderen Prozess gesperrt wird, könnte sie nicht obwohl `_access_s` gibt 0 zugreifen.  
  
 `_waccess_s` ist eine Breitzeichen\-Version von `_access_s`, wobei das Argument `path` von `_waccess_s` eine Zeichenfolge mit Breitzeichen ist.  Andernfalls verhalten sich `_waccess_s` und `_access_s` identisch.  
  
 Diese Funktionen überprüfen ihre Parameter.  Wenn `path``NULL` ist, oder `mode` kein gültiger Modus angibt, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_access_s`|\<io.h\>|\<errno.h\>|  
|`_waccess_s`|\<wchar.h oder\> io.h \<\>|\<errno.h\>|  
  
## Beispiel  
 In diesem Beispiel wird `_access_s` verwendet, um die Datei zu überprüfen, die crt\_access\_s.c, um festzustellen genannt wird, ob sie vorhanden ist und dass das Schreiben zulässt wird.  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
  **Datei crt\_access\_s.c vorhanden ist.**  
**Datei crt\_access\_s.c ist kein Schreibzugriff möglich.**   
## .NET Framework-Entsprechung  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat\- und \_wstat\-Funktionen](../../c-runtime-library/reference/stat-functions.md)