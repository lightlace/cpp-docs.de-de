---
title: "_rmdir, _wrmdir | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wrmdir"
  - "_rmdir"
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
  - "trmdir"
  - "_trmdir"
  - "wrmdir"
  - "_rmdir"
  - "_wrmdir"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rmdir-Funktion"
  - "_trmdir-Funktion"
  - "_wrmdir-Funktion"
  - "Verzeichnisse [C++], Löschen"
  - "Verzeichnisse [C++], Entfernen"
  - "rmdir-Funktion"
  - "trmdir-Funktion"
  - "wrmdir-Funktion"
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _rmdir, _wrmdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Löscht ein Verzeichnis.  
  
## Syntax  
  
```  
  
      int _rmdir(  
   const char *dirname   
);  
int _wrmdir(  
   const wchar_t *dirname   
);  
```  
  
#### Parameter  
 `dirname`  
 Pfad des zu entfernenden Verzeichnisses.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt 0 zurück, wenn das Verzeichnis gelöscht wird.  Bei dem Rückgabewert von 1 gibt einen Fehler an und `errno` auf einen der folgenden Werte festgelegt:  
  
 **ENOTEMPTY**  
 Der angegebene Pfad ist kein Verzeichnis, ist das Verzeichnis nicht leer, oder das Verzeichnis ist entweder das aktuelle Arbeitsverzeichnis oder das Stammverzeichnis.  
  
 `ENOENT`  
 Pfad ist ungültig.  
  
 **EACCES**  
 Ein Programm verfügt ein geöffnetes Handle das Verzeichnis.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Funktion `_rmdir` löscht das Verzeichnis, das von `dirname` angegeben wird.  Das Verzeichnis muss leer sein, und er darf nicht das aktuelle Arbeitsverzeichnis oder das Stammverzeichnis sein.  
  
 `_wrmdir` ist eine Breitzeichenversion von `_rmdir`. Das `dirname`\-Argument für `_wrmdir` ist eine Breitzeichenfolge.  `_wrmdir` und `_rmdir` verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_trmdir`|`_rmdir`|`_rmdir`|`_wrmdir`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_rmdir`|\<direct.h\>|  
|`_wrmdir`|\<direct.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Im Beispiel für [\_mkdir](../../c-runtime-library/reference/mkdir-wmkdir.md).  
  
## .NET Framework-Entsprechung  
 [System::IO::Directory::Delete](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)  
  
## Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)