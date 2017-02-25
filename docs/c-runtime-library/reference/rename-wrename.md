---
title: "rename, _wrename | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "rename"
  - "_wrename"
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
  - "_wrename"
  - "_trename"
  - "Rename"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_trename-Funktion"
  - "_wrename-Funktion"
  - "Verzeichnisse [C++], Umbenennen"
  - "Dateien [C++], Umbenennen"
  - "Namen [C++], Veränderliches Verzeichnis"
  - "Namen [C++], Veränderliche Datei"
  - "rename-Funktion"
  - "Umbenennen von Verzeichnissen"
  - "Umbenennen von Dateien"
  - "trename-Funktion"
  - "wrename-Funktion"
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# rename, _wrename
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nennen Sie eine Datei oder ein Verzeichnis um.  
  
## Syntax  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### Parameter  
 *oldname*  
 Zeiger dem alten Namen.  
  
 *Neuer Name*  
 Zeiger zum neuen Namen.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt 0 zurück, wenn es erfolgreich ist.  Auf einem Fehler gibt die Funktion einen Wert ungleich 0 \(null\) zurück und legt `errno` auf einen der folgenden Werte fest:  
  
 `EACCES`  
 Die Datei oder Verzeichnis, die von *newname* bereits angegeben werden, besteht oder konnte nicht erstellt \(Ungültige Pfad\); oder *oldname* ist ein Verzeichnis und *newname* gibt einem anderen Pfad.  
  
 `ENOENT`  
 Datei oder Pfad durch *das oldname* nicht gefunden.  
  
 `EINVAL`  
 Name enthält unzulässige Zeichen.  
  
 Für weitere mögliche Rückgabewerte finden Sie unter [\_doserrno, \_errno, syserrlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die **umbenennen**\-Funktion wird die Datei oder das Verzeichnis, um die von *oldname* den Namen angegeben ist, der von *newname* angegeben wird.  Der alte Name muss der Pfad einer vorhandenen Datei oder des Verzeichnisses befinden.  Der neue Name darf keinen Namen einer vorhandenen Datei oder des Verzeichnisses befinden.  Sie können **umbenennen** verwenden, um eine Datei aus einem Verzeichnis oder Geräten auf eine andere verschieben, indem Sie einen anderen Pfad im *newname*\-Argument geben.  Sie können **umbenennen** nicht verwenden, um ein Verzeichnis zu verschieben.  Verzeichnisse können umbenannt, jedoch nicht verschoben werden.  
  
 `_wrename` ist eine Breitzeichen\-Version von **\_rename**; die Argumente für `_wrename` sind Zeichenfolgen mit Breitzeichen.  `_wrename` und **\_rename** identisch verhalten sich andernfalls.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_trename`|**umbenennen**|**umbenennen**|`_wrename`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**umbenennen**|\<io.h oder\> stdio.h \<\>|  
|`_wrename`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## Ausgabe  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## .NET Framework-Entsprechung  
 [System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)