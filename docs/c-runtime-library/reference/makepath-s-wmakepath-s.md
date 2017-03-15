---
title: "_makepath_s, _wmakepath_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmakepath_s"
  - "_makepath_s"
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
  - "_wmakepath_s"
  - "makepath_s"
  - "_makepath_s"
  - "wmakepath_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_makepath_s-Funktion"
  - "wmakepath_s-Funktion"
  - "Pfade"
  - "_wmakepath_s-Funktion"
  - "makepath_s-Funktion"
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _makepath_s, _wmakepath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt einen Pfadnamen aus den Komponenten.  Diese Versionen sind von [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _makepath_s(  
   char *path,  
   size_t sizeInBytes,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
errno_t _wmakepath_s(  
   wchar_t *path,  
   size_t sizeInWords,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
template <size_t size>  
errno_t _makepath_s(  
   char (&path)[size],  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
); // C++ only  
template <size_t size>  
errno_t _wmakepath_s(  
   wchar_t (&path)[size],  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
); // C++ only  
```  
  
#### Parameter  
 \[out\] `path`  
 Puffer des vollständigen Pfads.  
  
 \[in\] `sizeInWords`  
 Größe des Puffers in Worten.  
  
 \[in\] `sizeInBytes`  
 Größe des Puffers in Bytes.  
  
 \[in\] `drive`  
 Enthält einen Buchstaben \(A, B, z.\) nach dem gewünschten Laufwerk und einem optionalen nachfolgenden Doppelpunkt.  `_makepath_s` fügt den Doppelpunkt automatisch im zusammengesetzten Pfad ein, falls es fehlt.  Wenn `drive``NULL` ist oder auf einer leeren Zeichenfolge verweist, wird kein Laufwerkbuchstabe in der zusammengesetzten `path` Zeichenfolge.  
  
 \[in\] `dir`  
 Enthält den Pfad von Verzeichnissen, ohne den Laufwerkbezeichner oder den tatsächlichen Dateinamen.  Der Schrägstrich nachgestellte ist optional und entweder ein Schrägstrich \(\/\) oder ein umgekehrter Schrägstrich \(\\\) oder beide können in einem einzelnen `dir`\-Argument verwendet werden.  Wenn kein nachgestellter Schrägstrich \(\\ oder\/\) angegeben wird, wird er automatisch eingefügt.  Wenn `dir``NULL` ist oder auf einer leeren Zeichenfolge verweist, wird kein Verzeichnispfad in der zusammengesetzten `path` Zeichenfolge eingefügt.  
  
 \[in\] `fname`  
 Enthält den Basisdateinamen ohne Dateinamenerweiterungen.  Wenn `fname``NULL` ist oder auf einer leeren Zeichenfolge verweist, wird kein Dateiname in der zusammengesetzten `path` Zeichenfolge eingefügt.  
  
 \[in\] `ext`  
 Enthält die tatsächliche Dateinamenerweiterung, mit oder ohne einen führenden Punkt \(.\).  `_makepath_s` fügt den Punkt automatisch, wenn sie nicht in `ext` angezeigt.  Wenn `ext``NULL` ist oder auf einer leeren Zeichenfolge verweist, wird keine der Erweiterung in zusammengesetzten `path` Zeichenfolge eingefügt.  
  
## Rückgabewert  
 Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.  
  
### Fehlerbedingungen  
  
|`path`|`sizeInWords` \/ `sizeInBytes`|Return|Inhalt von `path`|  
|------------|------------------------------------|------------|-----------------------|  
|`NULL`|any|`EINVAL`|nicht geändert|  
|any|\<\= 0|`EINVAL`|nicht geändert|  
  
 Wenn eine der oben genannten Fehlerzustände, tritt diese Funktionen aufrufen den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno` auf `EINVAL` festgelegt und die Funktion gibt `EINVAL` **zurück.** `NULL` ist für die Parameter `drive`, `fname` und `ext` zulässig.  Informationen über das Verhalten, wenn diese Parameter NULL\-Zeiger oder leere Zeichenfolgen sind, finden Sie im Abschnitt Hinweise.  
  
## Hinweise  
 Die `_makepath_s`\-Funktion erstellt eine zusammengesetzte Pfadzeichenfolge von den einzelnen Komponenten und das Ergebnis in `path`.  `path` könnte einen Laufwerkbuchstaben, einen Verzeichnispfad, einen Dateinamen und die Dateinamenerweiterung ein.  `_wmakepath_s` ist eine Breitzeichenversion von `_makepath_s`. Die Argumente für `_wmakepath_s` sind Zeichenfolgen mit Breitzeichen.  `_wmakepath_s` und `_makepath_s` verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tmakepath_s`|`_makepath_s`|`_makepath_s`|`_wmakepath_s`|  
  
 Das Argument `path` muss sich in einem leeren Puffer zeigen, der ausreicht, um den vollständigen Pfad groß ist.  Zusammengesetzte `path` muss als die `_MAX_PATH` Konstante nicht größer sein, die in Stdlib.h.  
  
 Wenn path `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Darüber hinaus wird `errno` auf `EINVAL` festgelegt.  `NULL`\-Werte werden für alle anderen Parameter zulässig.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf.  Mit [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) deaktivieren Sie dieses Verhalten.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_makepath_s`|\<stdlib.h\>|  
|`_wmakepath_s`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_makepath_s.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
   errno_t err;  
  
   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",  
                      "crt_makepath_s", "c" );  
   if (err != 0)  
   {  
      printf("Error creating path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );  
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,  
                       _MAX_FNAME, ext, _MAX_EXT );  
   if (err != 0)  
   {  
      printf("Error splitting the path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path extracted with _splitpath_s:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
## Ausgabe  
  
```  
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c  
  
Path extracted with _splitpath_s:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: crt_makepath_s  
  Ext: .c  
```  
  
## .NET Framework-Entsprechung  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)