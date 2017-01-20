---
title: "_unlock_file"
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
  - "_unlock_file"
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
  - "_unlock_file"
  - "unlock_file"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_unlock_file-Funktion"
  - "Dateien [C++], Entsperren"
  - "unlock_file-Funktion"
  - "Entsperren von Dateien"
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# _unlock_file
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt eine Datei frei und kann anderen Prozessen, um auf die Datei zuzugreifen.  
  
## Syntax  
  
```  
void _unlock_file(  
   FILE* file  
);  
```  
  
#### Parameter  
 `file`  
 Dateihandle.  
  
## Hinweise  
 Die `_unlock_file`\-Funktion wird die Datei freigeben, die von `file` angegeben wird.  Das Entsperren einer Datei können Zugriff auf die Datei durch andere Prozesse.  Diese Funktion sollte nicht aufgerufen werden, es sei denn, `_lock_file` zuvor um den Zeiger `file` aufgerufen wurde.  Das Aufrufen von `_unlock_file` in einer Datei, die nicht gesperrt wird, kann zu einem Deadlock.  Ein Beispiel finden Sie unter [\_lock\_file](../../c-runtime-library/reference/lock-file.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_unlock_file`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_lock\_file](../../c-runtime-library/reference/lock-file.md)