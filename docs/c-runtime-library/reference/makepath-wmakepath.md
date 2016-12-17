---
title: "_makepath, _wmakepath"
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
  - "_makepath"
  - "_wmakepath"
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
  - "_wmakepath"
  - "_tmakepath"
  - "makepath"
  - "tmakepath"
  - "wmakepath"
  - "_makepath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_makepath-Funktion"
  - "_tmakepath-Funktion"
  - "_wmakepath-Funktion"
  - "makepath-Funktion"
  - "Pfade"
  - "tmakepath-Funktion"
  - "wmakepath-Funktion"
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# _makepath, _wmakepath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellen Sie einen Pfadnamen aus den Komponenten.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## Syntax  
  
```  
void _makepath(  
   char *path,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
void _wmakepath(  
   wchar_t *path,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
```  
  
#### Parameter  
 `path`  
 Puffer des vollständigen Pfads.  
  
 `drive`  
 Enthält einen Buchstaben \(A, B, z.\) nach dem gewünschten Laufwerk und einem optionalen nachfolgenden Doppelpunkt.  `_makepath` fügt den Doppelpunkt automatisch im zusammengesetzten Pfad ein, falls es fehlt.  Wenn `drive``NULL` ist oder auf einer leeren Zeichenfolge verweist, wird kein Laufwerkbuchstabe in der zusammengesetzten `path` Zeichenfolge.  
  
 `dir`  
 Enthält den Pfad von Verzeichnissen, ohne den Laufwerkbezeichner oder den tatsächlichen Dateinamen.  Der Schrägstrich nachgestellte ist optional und entweder ein Schrägstrich \(\/\) oder ein umgekehrter Schrägstrich \(\\\) oder beide können in einem einzelnen `dir`\-Argument verwendet werden.  Wenn kein nachgestellter Schrägstrich \(\\ oder\/\) angegeben wird, wird er automatisch eingefügt.  Wenn `dir``NULL` ist oder auf einer leeren Zeichenfolge verweist, wird kein Verzeichnispfad in der zusammengesetzten `path` Zeichenfolge eingefügt.  
  
 `fname`  
 Enthält den Basisdateinamen ohne Dateinamenerweiterungen.  Wenn `fname``NULL` ist oder auf einer leeren Zeichenfolge verweist, wird kein Dateiname in der zusammengesetzten `path` Zeichenfolge eingefügt.  
  
 `ext`  
 Enthält die tatsächliche Dateinamenerweiterung, mit oder ohne einen führenden Punkt \(.\).  `_makepath` fügt den Punkt automatisch, wenn sie nicht in `ext` angezeigt.  Wenn `ext``NULL` ist oder auf einer leeren Zeichenfolge verweist, wird keine der Erweiterung in zusammengesetzten `path` Zeichenfolge eingefügt.  
  
## Hinweise  
 Die `_makepath`\-Funktion erstellt eine zusammengesetzte Pfadzeichenfolge von den einzelnen Komponenten und das Ergebnis in `path`.  `path` könnte einen Laufwerkbuchstaben, einen Verzeichnispfad, einen Dateinamen und die Dateinamenerweiterung ein.  `_wmakepath` ist eine Breitzeichenversion von `_makepath`. Die Argumente für `_wmakepath` sind Zeichenfolgen mit Breitzeichen.  `_wmakepath` und `_makepath` verhalten sich andernfalls identisch.  
  
 **Sicherheitshinweis** Verwenden Sie eine auf NULL abschließende Zeichenfolge.  Pufferüberlauf Um zu vermeiden, darf die auf NULL abschließende Zeichenfolge die Größe des Puffers `path` nicht überschreiten.  `_makepath` garantiert nicht, dass die Länge der Pfadzeichenfolge nicht zusammengesetzten `_MAX_PATH` überschreitet.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 Das Argument `path` muss sich in einem leeren Puffer zeigen, der ausreicht, um den vollständigen Pfad groß ist.  Zusammengesetzte `path` muss als die `_MAX_PATH` Konstante nicht größer sein, die in Stdlib.h.  
  
 Wenn path `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Darüber hinaus wird `errno` auf `EINVAL` festgelegt.  `NULL`\-Werte werden für alle anderen Parameter zulässig.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_makepath`|\<stdlib.h\>|  
|`_wmakepath`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_makepath.c  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
  
   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996  
   // Note: _makepath is deprecated; consider using _makepath_s instead  
   printf( "Path created with _makepath: %s\n\n", path_buffer );  
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996  
   // Note: _splitpath is deprecated; consider using _splitpath_s instead  
   printf( "Path extracted with _splitpath:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
  **Pfad erstellt mit \_makepath: c:\\sample\\crt\\makepath.c**  
**Pfad extrahiert mit \_splitpath:**  
 **Laufwerk: c:**  
 **Dir: \\sample\\crt\\**  
 **Dateiname: makepath**  
 **Ext: C**   
## .NET Framework-Entsprechung  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)