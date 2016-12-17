---
title: "_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32"
ms.custom: na
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_wstat64"
  - "_stati64"
  - "_stat32"
  - "_stat32i64"
  - "_stat"
  - "_wstati64"
  - "_wstat32"
  - "_wstat64i32"
  - "_wstat"
  - "_stat64"
  - "_stat64i32"
  - "_wstat32i64"
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
  - "tstat32"
  - "tstat"
  - "_tstat64i32"
  - "tstati64"
  - "_wstat64"
  - "_wstat32"
  - "wstati64"
  - "tstat64"
  - "_stati64"
  - "_wstat"
  - "wstat64i32"
  - "stat32i64"
  - "tstat32i64"
  - "_tstat"
  - "_wstati64"
  - "_tstati64"
  - "_wstat32i64"
  - "wstat32"
  - "_wstat64i32"
  - "_stat"
  - "_tstat32"
  - "stat64i32"
  - "wstat64"
  - "stat"
  - "_stat32i64"
  - "_stat32"
  - "stati64"
  - "wstat"
  - "_stat64i32"
  - "stat32"
  - "_tstat32i64"
  - "tstat64i32"
  - "_tstat64"
  - "_stat64"
  - "stat/_stat"
  - "stat/_stat32"
  - "stat/_stat64"
  - "stat/_stati64"
  - "stat/_stat32i64"
  - "stat/_stat64i32"
  - "stat/_wstat"
  - "stat/_wstat32"
  - "stat/_wstat64"
  - "stat/_wstati64"
  - "stat/_wstat32i64"
  - "stat/_wstat64i32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Dateien [C++], Statusinformation"
  - "_stat-Funktion"
  - "_wstat-Funktion"
  - "_stat64i32-Funktion"
  - "tstat-Funktion"
  - "_tstat64i32-Funktion"
  - "_stati64-Funktion"
  - "_stat64-Funktion"
  - "tstati64-Funktion"
  - "wstati64-Funktion"
  - "wstat64-Funktion"
  - "_wstat64i32-Funktion"
  - "_tstat32i64-Funktion"
  - "_stat32i64-Funktion"
  - "stat-Funktion"
  - "Status der Dateien"
  - "_tstat32-Funktion"
  - "tstat64-Funktion"
  - "_wstat64-Funktion"
  - "_tstat-Funktion"
  - "_stat32-Funktion"
  - "wstat-Funktion"
  - "_wstat32i64-Funktion"
  - "_tstati64-Funktion"
  - "_wstat32-Funktion"
  - "stat64-Funktion"
  - "stati64-Funktion"
  - "_wstati64-Funktion"
  - "_tstat64-Funktion"
  - "Dateien [C++], Abrufen von Statusinformation"
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
caps.latest.revision: 26
caps.handback.revision: "26"
ms.author: "corob"
manager: "ghogen"
---
# _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abrufen von Statusinformationen zu einer Datei.  
  
## Syntax  
  
```  
int _stat(  
   const char *path,  
   struct _stat *buffer   
);  
int _stat32(  
   const char *path,  
   struct __stat32 *buffer   
);  
int _stat64(  
   const char *path,  
   struct __stat64 *buffer   
);  
int _stati64(  
   const char *path,  
   struct _stati64 *buffer   
);  
int _stat32i64(  
   const char *path,  
   struct _stat32i64 *buffer   
);  
int _stat64i32(  
   const char *path,  
   struct _stat64i32 *buffer   
);  
int _wstat(  
   const wchar_t *path,  
   struct _stat *buffer   
);  
int _wstat32(  
   const wchar_t *path,  
   struct __stat32 *buffer   
);  
int _wstat64(  
   const wchar_t *path,  
   struct __stat64 *buffer   
);  
int _wstati64(  
   const wchar_t *path,  
   struct _stati64 *buffer   
);  
int _wstat32i64(  
   const wchar_t *path,  
   struct _stat32i64 *buffer   
);  
int _wstat64i32(  
   const wchar_t *path,  
   struct _stat64i32 *buffer   
);  
```  
  
#### Parameter  
 `path`  
 Ein Zeiger auf eine Zeichenfolge, die den Pfad einer vorhandenen Datei oder eines vorhandenen Verzeichnisses enthält.  
  
 `buffer`  
 Ein Zeiger auf die Struktur, in der die Ergebnisse gespeichert werden.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt „0“ zurück, wenn die Dateistatusinformationen abgerufen werden. Ein Rückgabewert von „–1“ zeigt einen Fehler an. In diesem Fall wird `errno` auf `ENOENT` festgelegt, was anzeigt, dass der Dateiname oder Pfad nicht gefunden werden konnte. Der Rückgabewert `EINVAL` zeigt einen ungültigen Parameter an; `errno` wird in diesem Fall ebenfalls auf `EINVAL` festgelegt.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Der Datumsstempel einer Datei dargestellt werden kann, ist er höher als Mitternacht, 1. Januar 1970 und vor 23:59:59, 31. Dezember 3000, UTC, es sei denn, Sie verwenden `_stat32` oder `_wstat32`, oder eine `_USE_32BIT_TIME_T`, in diesem Fall das Datum nur bis 23:59:59 am 18. Januar 2038 UTC dargestellt werden kann.  
  
## Hinweise  
 Die `_stat`\-Funktion ruft Informationen zur durch `path` angegebenen Datei bzw. dem angegebenen Verzeichnis ab und speichert sie in der Struktur, auf die `buffer` verweist.`_stat` behandelt Multibyte\-Zeichenfolgenargumente automatisch richtig. Die Erkennung von Multibyte\-Zeichenfolgen erfolgt auf der Grundlage der aktuell verwendeten Multibyte\-Codeseite.  
  
 `_wstat` ist eine Breitzeichenversion von `_stat`. Das `path`\-Argument für `_wstat` ist eine Breitzeichenfolge.`_wstat` und `_stat` verhalten sich identisch, mit dem Unterschied, dass `_wstat` keine Multibyte\-Zeichenfolgen verarbeitet.  
  
 Varianten dieser Funktionen unterstützen 32\-Bit\- oder 64\-Bit\-Zeittypen und 32\-Bit\- oder 64\-Bit\-Dateilängen. Das erste numerische Suffix \(`32` oder `64`\) gibt die Größe des verwendeten Zeittyps an; das zweite Suffix ist entweder `i32` oder `i64` und gibt an, ob die Dateigröße als ganze Zahl mit 32 Bit oder 64 Bit dargestellt ist.  
  
 `_stat` entspricht dem `_stat64i32`, und `struct``_stat` enthält eine 64\-Bit\-Uhrzeit. Dies ist der Fall, wenn `_USE_32BIT_TIME_T` definiert ist, wird in diesem Fall wird das alte Verhalten aktiviert; `_stat` verwendet eine 32\-Bit\-Zeit und `struct``_stat` enthält eine 32\-Bit\-Uhrzeit. Gleiches gilt auch für `_stati64`.  
  
> [!NOTE]
>  `_wstat` funktioniert nicht mit symbolischen [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]\-Verknüpfungen. In diesen Fällen meldet `_wstat` immer die Dateigröße „0“.`_stat` funktioniert mit symbolischen Verknüpfungen nicht ordnungsgemäß.  
  
 Diese Funktion überprüft ihre Parameter. Wenn entweder `path` oder `buffer` den Wert `NULL` aufweist, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
### \_stat\-Variationen des Uhrzeittyps und Dateilängentyps  
  
|Funktionen|\_USE\_32BIT\_TIME\_T definiert?|Uhrzeittyp|Dateilängentyp|  
|----------------|--------------------------------------|----------------|--------------------|  
|`_stat`, `_wstat`|Nicht definiert|64\-Bit|32\-Bit|  
|`_stat`, `_wstat`|Definiert|32\-Bit|32\-Bit|  
|`_stat32`, `_wstat32`|Nicht von der Makrodefinition betroffen|32\-Bit|32\-Bit|  
|`_stat64`, `_wstat64`|Nicht von der Makrodefinition betroffen|64\-Bit|64\-Bit|  
|`_stati64`, `_wstati64`|Nicht definiert|64\-Bit|64\-Bit|  
|`_stati64`, `_wstati64`|Definiert|32\-Bit|64\-Bit|  
|`_stat32i64`, `_wstat32i64`|Nicht von der Makrodefinition betroffen|32\-Bit|64\-Bit|  
|`_stat64i32`, `_wstat64i32`|Nicht von der Makrodefinition betroffen|64\-Bit|32\-Bit|  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tstat`|`_stat`|`_stat`|`_wstat`|  
|`_tstat64`|`_stat64`|`_stat64`|`_wstat64`|  
|`_tstati64`|`_stati64`|`_stati64`|`_wstati64`|  
|`_tstat32i64`|`_stat32i64`|`_stat32i64`|`_wstat32i64`|  
|`_tstat64i32`|`_stat64i32`|`_stat64i32`|`_wstat64i32`|  
  
 Die in SYS\\STAT.h definierte Struktur `_stat` enthält die folgenden Felder.  
  
 `st_gid`  
 Numerischer Bezeichner der Gruppe, die die Datei besitzt \(UNIX\-spezifisch\). Dieses Feld weist auf Windows\-Systemen immer den Wert „0“ \(null\) auf. Eine umgeleitete Datei wird als Windows\-Datei klassifiziert.  
  
 `st_atime`  
 Zeitpunkt des letzten Zugriffs auf die Datei. Gültig auf NTFS\-, aber nicht auf FAT\-formatierten Laufwerken.  
  
 `st_ctime`  
 Uhrzeit der Dateierstellung. Gültig auf NTFS\-, aber nicht auf FAT\-formatierten Laufwerken.  
  
 `st_dev`  
 Laufwerksnummer des Datenträgers, der die Datei enthält \(gleichbedeutend mit `st_rdev`\).  
  
 `st_ino`  
 Anzahl der Informationsknoten \(der `inode`s\) für die Datei \(UNIX\-spezifisch\). Bei UNIX\-Dateisystemen beschreibt der `inode` die Dateistempel für Datum und Uhrzeit, die Berechtigungen und den Inhalt. Wenn Dateien durch einen festen Link miteinander verknüpft sind, besitzen sie den gleichen `inode`. Der `inode` und daher auch `st_ino` ist bei den Dateisystemen FAT, HPFS oder NTFS ohne Bedeutung.  
  
 `st_mode`  
 Bitmaske für Dateimodusinformationen. Das `_S_IFDIR`\-Bit ist festgelegt, wenn `path` ein Verzeichnis angibt; das `_S_IFREG`\-Bit ist festgelegt, wenn `path` eine gewöhnliche Datei oder ein Gerät angibt. Lese\-\/Schreibbits für Benutzer werden entsprechend dem Berechtigungsmodus der Datei festgelegt; Ausführungsbits für Benutzer werden entsprechend der Dateierweiterung festgelegt.  
  
 `st_mtime`  
 Uhrzeit der letzten Änderung der Datei.  
  
 `st_nlink`  
 Bei Nicht\-NTFS\-Dateisystemen immer „1“.  
  
 `st_rdev`  
 Laufwerksnummer des Datenträgers, der die Datei enthält \(gleicher Wert wie `st_dev`\).  
  
 `st_size`  
 Größe der Datei in Byte; eine ganze 64\-Bit\-Zahl für Varianten mit dem `i64`\-Suffix**.**  
  
 `st_uid`  
 Numerischer Bezeichner des Benutzers, der die Datei besitzt \(UNIX\-spezifisch\). Dieses Feld hat bei Windows\-Systemen immer den Wert „0“. Eine umgeleitete Datei wird als Windows\-Datei klassifiziert.  
  
 Wenn `path` auf ein Gerät verweist, haben die Felder `st_size`, die verschiedenen Zeitfelder, `st_dev` und `st_rdev` in der `_stat`\-Struktur keine Bedeutung. Da „STAT.H“ den [\_dev\_t](../../c-runtime-library/standard-types.md)\-Typ verwendet, der in „TYPES.H“ definiert ist, müssen Sie „TYPES.H“ vor „STAT.H“ in Ihrem Code einschließen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`_stat`, `_stat32`, `_stat64`, `_stati64`, `_stat32i64`, `_stat64i32`|\<sys\/types.h\> gefolgt von \<sys\/stat.h\>|\<errno.h\>|  
|`_wstat`, `_wstat32`, `_wstat64`, `_wstati64`, `_wstat32i64`, `_wstat64i32`|\<sys\/types.h\> gefolgt von \<sys\/stat.h\> oder \<wchar.h\>|\<errno.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_stat.c  
// This program uses the _stat function to  
// report information about the file named crt_stat.c.  
  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int result;  
   char timebuf[26];  
   char* filename = "crt_stat.c";  
   errno_t err;  
  
   // Get data associated with "crt_stat.c":   
   result = _stat( filename, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      perror( "Problem getting information" );  
      switch (errno)  
      {  
         case ENOENT:  
           printf("File %s not found.\n", filename);  
           break;  
         case EINVAL:  
           printf("Invalid parameter to _stat.\n");  
           break;  
         default:  
           /* Should never be reached. */  
           printf("Unexpected error in _stat.\n");  
      }  
   }  
   else  
   {  
      // Output some of the statistics:   
      printf( "File size     : %ld\n", buf.st_size );  
      printf( "Drive         : %c:\n", buf.st_dev + 'A' );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid arguments to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
}  
```  
  
```Output  
Dateigröße     : 732 Laufwerk         : C: Uhrzeit der Änderung : Do. 7. Feb 14:39:36 2002  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx)  
  
-   [System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx)  
  
-   [System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx)  
  
-   [System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)