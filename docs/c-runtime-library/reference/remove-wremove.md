---
title: "remove, _wremove | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wremove"
  - "remove"
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
  - "remove"
  - "_wremove"
  - "_tremove"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tremove-Funktion"
  - "_wremove-Funktion"
  - "Dateien [C++], Löschen"
  - "Dateien [C++], Entfernen"
  - "remove-Funktion"
  - "tremove-Funktion"
  - "wremove-Funktion"
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# remove, _wremove
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Löschen einer Datei  
  
## Syntax  
  
```  
  
      int remove(  
   const char *path   
);  
int _wremove(  
   const wchar_t *path   
);  
```  
  
#### Parameter  
 *path*  
 Pfad der zu entfernende Datei.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt 0 zurück, wenn die Datei erfolgreich gelöscht wird.  Andernfalls wird \-1 zurückgegeben und `errno` fest, auf das `EACCES`, um anzugeben jedes, ist, dass der Pfad eine schreibgeschützte Datei angibt, oder die Datei geöffnet ist, oder auf **ENOENT**  festzulegen, ob der Dateiname oder der Pfad nicht gefunden wurden, oder dass der Pfad einem Verzeichnis angibt.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die **Entfernen**\-Funktion wird die Datei, die vom *Pfad* angegeben.  `_wremove` ist eine Breitzeichen\-Version von **\_remove**; das *Pfad* argument zu `_wremove` ist eine Zeichenfolge mit Breitzeichen.  `_wremove` und **\_remove** identisch verhalten sich andernfalls.  Alle Handles zu einer Datei muss geschlossen werden, bevor sie gelöscht werden kann.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tremove`|**remove**|**remove**|`_wremove`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**remove**|\<stdio.h oder\> io.h \<\>|  
|`_wremove`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_remove.c  
/* This program uses remove to delete crt_remove.txt */  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( remove( "crt_remove.txt" ) == -1 )  
      perror( "Could not delete 'CRT_REMOVE.TXT'" );  
   else  
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );  
}  
```  
  
## Eingabe: crt\_remove.txt  
  
```  
This file will be deleted.  
```  
  
## Beispielausgabe  
  
```  
Deleted 'CRT_REMOVE.TXT'  
```  
  
## .NET Framework-Entsprechung  
 [System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_unlink, \_wunlink](../../c-runtime-library/reference/unlink-wunlink.md)