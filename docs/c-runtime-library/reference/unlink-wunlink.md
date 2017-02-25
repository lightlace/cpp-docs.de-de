---
title: "_unlink, _wunlink | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_unlink"
  - "_wunlink"
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
  - "_tunlink"
  - "_unlink"
  - "wunlink"
  - "_wunlink"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tunlink-Funktion"
  - "_unlink-Funktion"
  - "_wunlink-Funktion"
  - "Dateien [C++], Löschen"
  - "Dateien [C++], Entfernen"
  - "tunlink-Funktion"
  - "unlink-Funktion"
  - "wunlink-Funktion"
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _unlink, _wunlink
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Löschen einer Datei  
  
## Syntax  
  
```  
int _unlink(  
   const char *filename   
);  
int _wunlink(  
   const wchar_t *filename   
);  
```  
  
#### Parameter  
 `filename`  
 Name der zu entfernende Datei.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt 0 zurück, wenn der Vorgang erfolgreich ist.  Andernfalls wird die Funktion \- 1 zurück und legt `errno` auf `EACCES` fest, was bedeutet, dass der Pfad eine schreibgeschützte Datei angibt oder `ENOENT`, die besagt, die Datei oder der Pfad nicht gefunden wird, oder der Pfad ein Verzeichnis angegeben.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_unlink`\-Funktion wird die Datei, die von `filename` angegeben wird.  `_wunlink` ist eine Breitzeichenversion von `_unlink`. Das `filename`\-Argument für `_wunlink` ist eine Breitzeichenfolge.  Anderenfalls verhalten sich diese Funktionen identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tunlink`|`_unlink`|`_unlink`|`_wunlink`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_unlink`|\<io.h und\> stdio.h \<\>|  
|`_wunlink`|\<io.h oder\> wchar.h \<\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Codebeispiel  
 Dieses Programm verwendet \_unlink, um CRT\_UNLINK.TXT zu löschen.  
  
```  
// crt_unlink.c  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( _unlink( "crt_unlink.txt" ) == -1 )  
      perror( "Could not delete 'CRT_UNLINK.TXT'" );  
   else  
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );  
}  
```  
  
### Eingabe: crt\_unlink.txt  
  
```  
This file will be deleted.  
```  
  
### Beispielausgabe  
  
```  
Deleted 'CRT_UNLINK.TXT'  
```  
  
## .NET Framework-Entsprechung  
 [System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [remove, \_wremove](../../c-runtime-library/reference/remove-wremove.md)