---
title: "_fullpath, _wfullpath"
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
  - "_fullpath"
  - "_wfullpath"
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
  - "wfullpath"
  - "fullpath"
  - "_wfullpath"
  - "_fullpath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fullpath-Funktion"
  - "_wfullpath-Funktion"
  - "Absolute Pfade"
  - "Vollpfadfunktion"
  - "Relative Dateipfade"
  - "wfullpath-Funktion"
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 18
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# _fullpath, _wfullpath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt ein absoluter oder einen vollständigen Pfadnamen für den angegebenen relativen Pfadnamen.  
  
## Syntax  
  
```  
char *_fullpath(   
   char *absPath,  
   const char *relPath,  
   size_t maxLength   
);  
wchar_t *_wfullpath(   
   wchar_t *absPath,  
   const wchar_t *relPath,  
   size_t maxLength   
);  
```  
  
#### Parameter  
 `absPath`  
 Zeiger auf einen Puffer, der das Absolute oder der vollständige Pfadname oder NULL enthält.  
  
 `relPath`  
 Relativer Pfadname.  
  
 `maxLength`  
 Maximale Länge des absoluten Pfadnamenpuffers \(`absPath`\).  Diese Länge ist in Bytes für `_fullpath` in den Breitzeichen \(`wchar_t`\) für `_wfullpath`.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf einen Puffer zurück, der den absoluten Pfadnamen \(`absPath`\) enthält.  Wenn es einen Fehler \(beispielsweise, wenn der Wert, der an `relPath` übergeben wird, einen Laufwerkbuchstaben enthält, der NULL ist oder nicht gefunden werden kann, oder wenn die Länge des erstellten absoluten Pfadnamens \(`absPath`\), ist größer als `maxLength`\), gibt die Funktion `NULL` zurückgibt.  
  
## Hinweise  
 Die `_fullpath`\-Funktion erweitert den relativen Pfadnamen in `relPath` auf den vollqualifizierten oder absolute Pfad und speichert diesen Namen in `absPath`*.* Wenn `absPath` NULL ist, wird `malloc` verwendet, um einem ausreichenden Puffer der Länge zu, um den Pfadnamen aufzunehmen.  Es liegt in der Verantwortung des Aufrufers, diesem Puffer freizugeben.  Ein relativer Pfadname gibt einen Pfad zu einem anderen Speicherort von der aktuellen Position an \(wie zum aktuellen Arbeitsverzeichnis: "."\).  Ein absoluter Pfadname ist die Erweiterung eines relativen Pfadnamens, der den gesamten Pfad angibt, der erforderlich ist, um den gewünschten Speicherort dem Stamm des Dateisystems zu erreichen.  Anders als `_makepath` kann `_fullpath` verwendet werden, um den absoluten Pfadnamen für relative Pfade \(`relPath`\) erhalten können vorliegen ". \/" oder ". \/" in ihren Namen.  
  
 Um beispielsweise C\-Laufzeit\-Routinen zu verwenden, muss die Anwendung die Headerdateien enthalten, die die Deklarationen für die Routinen enthalten.  Jede Headerdateieinschließungsanweisung verweist auf den Speicherort der Datei in einer relativen Weise \(aus dem Arbeitsverzeichnis der Anwendung\):  
  
```  
#include <stdlib.h>  
```  
  
 als der absolute Pfad kann \(tatsächliche des Dateisystems der Datei ist\):  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath`  behandelt automatisch Mehrbyte\-Zeichenfolgen\-Argumente entsprechend und derzeit erkennt Mehrbytezeichensequenzen entsprechend der Mehrbyte\-Codepage.  `_wfullpath`  ist eine Breitzeichen\-Version von `_fullpath`; die Zeichenfolgenargumente für `_wfullpath`  sind Zeichenfolgen mit Breitzeichen.  `_wfullpath`  und `_fullpath`  identisch verhalten sich, dass `_wfullpath`  nicht behandelt Mehrbyte\-Zeichenfolgen.  
  
 Wenn `_DEBUG`  und `_CRTDBG_MAP_ALLOC`  beide definiert werden, werden Aufrufe von `_fullpath` und `_wfullpath` durch Aufrufe von `_fullpath_dbg` und `_wfullpath_dbg` ersetzt, um das Debuggen von Speicherbelegungen zuzulassen.  Weitere Informationen finden Sie unter [\_fullpath\_dbg, \_wfullpath\_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md).  
  
 Diese Funktion ruft den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, wenn `maxlen` kleiner oder gleich 0 ist.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `NULL` zurück.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 Wenn der Puffer `absPath` eine `NULL` ist, wird `_fullpath`[malloc](../../c-runtime-library/reference/malloc.md) auf, um einem Puffer reserviert und ignoriert das `maxLength`\-Argument.  Es liegt in der Verantwortung des Aufrufers, diesem Puffer nach Bedarf freizugeben \(mit [frei](../../c-runtime-library/reference/free.md)\).  Wenn `relPath` das Argument einem Laufwerk angibt, wird das aktuelle Verzeichnis dieses Laufwerks mit dem Pfad kombiniert.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fullpath`|\<stdlib.h\>|  
|`_wfullpath`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fullpath.c  
// This program demonstrates how _fullpath  
// creates a full path from a partial path.  
  
#include <stdio.h>  
#include <conio.h>  
#include <stdlib.h>  
#include <direct.h>  
  
void PrintFullPath( char * partialPath )  
{  
   char full[_MAX_PATH];  
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )  
      printf( "Full path is: %s\n", full );  
   else  
      printf( "Invalid path\n" );  
}  
  
int main( void )  
{  
   PrintFullPath( "test" );  
   PrintFullPath( "\\test" );  
   PrintFullPath( "..\\test" );  
}  
```  
  
  **Vollständiger Pfad ist: C:\\Dokumente und Einstellungen\\Benutzer\\Eigene Dokumente\\Test**  
**Vollständiger Pfad ist: C:\\test**  
**Vollständiger Pfad ist: C:\\Dokumente und Einstellungen\\Benutzer\\Test**   
## .NET Framework-Entsprechung  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)