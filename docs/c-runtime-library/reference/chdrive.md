---
title: "_chdrive"
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
  - "_chdrive"
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
  - "chdrive"
  - "_chdrive"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chdrive-Funktion"
  - "chdrive-Funktion"
  - "Laufwerke, Ändern"
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# _chdrive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert das aktuelle Laufwerk.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _chdrive(   
   int drive   
);  
```  
  
#### Parameter  
 `drive`  
 Eine ganze Zahl von 1 bis 26, die das aktuelle Laufwerk angibt \(1\=A, 2\=B usw.\).  
  
## Rückgabewert  
 Null \(0\), wenn das aktuelle Laufwerk erfolgreich geändert wurde; andernfalls – 1.  
  
## Hinweise  
 Wenn `drive` nicht im Bereich von 1 bis 26 liegt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt die **\_chdrive**\-Funktion – 1 zurück, `errno` wird auf `EACCES` gesetzt und `_doserrno` auf `ERROR_INVALID_DRIVE`.  
  
 Die **\_chdrive**\-Funktion ist nicht threadsicher, da sie von der **SetCurrentDirectory**\-Funktion abhängt, die selbst nicht threadsicher ist.  Um **\_chdrive** sicher in einer Multithreadanwendung zu verwenden, müssen Sie eine eigene Threadsynchronisierung bereitstellen.  Weitere Informationen finden Sie in der [MSDN Library](http://go.microsoft.com/fwlink/?LinkID=150542). Suchen Sie dort nach **SetCurrentDirectory**.  
  
 Die **\_chdrive**\-Funktion ändert nur das aktuelle Laufwerk; **\_chdir** ändert das aktuelle Arbeitsverzeichnis.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**\_chdrive**|\<direct.h\>|  
  
 Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Ein Beispiel hierfür finden Sie unter [\_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## .NET Framework-Entsprechung  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)