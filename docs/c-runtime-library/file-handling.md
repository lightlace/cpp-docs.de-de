---
title: "Dateibehandlung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.files"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dateien [C++], Behandlung"
  - "Dateien [C++], Bearbeiten"
  - "Dateien [C++], Öffnen"
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Dateibehandlung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Routinen zum Erstellen, Löschen und Bearbeiten von Dateien und zum Überprüfen der Dateizugriffsberechtigungen.  
  
 Bei C\-Laufzeitbibliotheken können maximal 512 Dateien gleichzeitig geöffnet sein. Wenn Sie versuchen, mehr als die maximale Anzahl von Dateideskriptoren oder Dateistreams zu öffnen, kommt es zu einem Programmfehler. Mit [\_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) können Sie diese Anzahl ändern.  
  
 Die folgenden Routinen werden auf Dateien ausgeführt, die durch einen Dateideskriptor festgelegt sind.  
  
### Dateibehandlungsroutinen \(Dateideskriptor\)  
  
|Routine|Verwendung|.NET Framework\-Entsprechung|  
|-------------|----------------|----------------------------------|  
|[\_chsize](../c-runtime-library/reference/chsize.md),[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|Dateigröße ändern|[System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx), [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)|  
|[\_filelength, \_filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|Dateilänge abrufen|[System::IO::Stream::Length](https://msdn.microsoft.com/en-us/library/system.io.stream.length.aspx), [System::IO::FileStream::Length](https://msdn.microsoft.com/en-us/library/system.io.filestream.length.aspx)|  
|[\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|Dateistatusinformationen zum Deskriptor abrufen|Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Betriebssystem\-Dateihandle zurückgeben, das vorhandenem C\-Laufzeit\-Dateideskriptor zugeordnet ist|Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_isatty](../c-runtime-library/reference/isatty.md)|Auf Zeichengerät überprüfen|[System::IO::Stream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.filestream.canwrite.aspx), [System::IO::FileStream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.stream.canwrite.aspx)|  
|[\_locking](../c-runtime-library/reference/locking.md)|Dateibereiche sperren|[System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C\-Laufzeit\-Dateideskriptor zu vorhandenem Betriebssystem\-Dateihandle zuordnen|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_setmode](../c-runtime-library/reference/setmode.md)|Dateiübersetzungsmodus festlegen|[System::IO::BinaryReader Class](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx), [System::IO::TextReader Class](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)|  
  
 Die folgenden Routinen werden auf Dateien ausgeführt, die durch einen Pfad oder einen Dateinamen angegeben sind.  
  
### Dateibehandlungsroutinen \(Pfad oder Dateiname\)  
  
|Routine|Verwendung|.NET Framework\-Entsprechung|  
|-------------|----------------|----------------------------------|  
|[\_access, \_waccess](../c-runtime-library/reference/access-waccess.md), [\_access\_s, \_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|Dateiberechtigungseinstellung überprüfen|[System::IO::FileAccess Enumeration](https://msdn.microsoft.com/en-us/library/4z36sx0f.aspx)|  
|[\_chmod, \_wchmod](../c-runtime-library/reference/chmod-wchmod.md)|Dateiberechtigungseinstellung ändern|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx), [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)|  
|[\_fullpath, \_wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|Relativen Pfad auf den absoluten Pfadnamen erweitern|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_makepath, \_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [\_makepath\_s, \_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Pfadkomponenten in einen einzelnen, vollständigen Pfad zusammenführen|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_mktemp, \_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [\_mktemp\_s, \_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Eindeutigen Dateinamen erstellen|Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[remove, \_wremove](../c-runtime-library/reference/remove-wremove.md)|Datei löschen|[System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
|[rename, \_wrename](../c-runtime-library/reference/rename-wrename.md)|Datei umbenennen|[System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)|  
|[\_splitpath, \_wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md), [\_splitpath\_s, \_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Pfad nach Komponenten analysieren|Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_stat, \_stat64, \_stati64, \_wstat, \_wstat64, \_wstati64](../c-runtime-library/reference/stat-functions.md)|Dateistatusinformationen zur benannten Datei abrufen|[System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx), [System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx), [System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx), [System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../c-runtime-library/reference/umask-s.md)|Standardberechtigungsmaske für neue Dateien festlegen, die vom Programm erstellt werden|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)|  
|[\_unlink, \_wunlink](../c-runtime-library/reference/unlink-wunlink.md)|Datei löschen|[System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
  
 Die folgenden Routinen dienen zum Öffnen von Dateien.  
  
### Dateibehandlungsroutinen \(geöffnete Datei\)  
  
|Routine|Verwendung|.NET Framework\-Entsprechung|  
|-------------|----------------|----------------------------------|  
|[fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Öffnet eine Datei und gibt einen Zeiger an die geöffnete Datei zurück.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.#ctor*>|  
|[\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Öffnet einen Stream mit Dateifreigabe und gibt einen Zeiger an die geöffnete Datei zurück.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.#ctor*>|  
|[\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)|Öffnet eine Datei und gibt einen Dateideskriptor an die geöffnete Datei zurück.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.#ctor*>|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Öffnet eine Datei mit Dateizugriff und gibt einen Dateideskriptor an die geöffnete Datei zurück.||  
|[\_pipe](../c-runtime-library/reference/pipe.md)|Erstellt eine Pipe zum Lesen und Schreiben.|Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s, \_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Weist einen Dateizeiger neu zu.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.#ctor*>|  
  
 Die folgenden Funktionen bieten eine Möglichkeit, die Darstellung der Datei zwischen einer `FILE`\-Struktur, einem Dateideskriptor und einem Win32\-Dateihandle zu ändern.  
  
||||  
|-|-|-|  
|[\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Ordnet einen Stream einer Datei zu, die zuvor für E\/A\-Unterstützung auf niedriger Ebene geöffnet wurde, und gibt einen Zeiger an den geöffneten Stream zurück.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.filestream.aspx)|  
|[\_fileno](../c-runtime-library/reference/fileno.md)|Ruft den Dateideskriptor ab, der einem Stream zugeordnet ist.|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Betriebssystem\-Dateihandle zurückgeben, das vorhandenem C\-Laufzeit\-Dateideskriptor zugeordnet ist|Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|Ordnet den C\-Laufzeit\-Dateideskriptor einem vorhandenen Betriebssystem\-Dateihandle zu.|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
  
 Mit den folgenden Win32\-Funktionen werden auch Dateien und Pipes geöffnet:  
  
-   [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858.aspx)  
  
-   [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)  
  
-   [CreateNamedPipe](http://msdn.microsoft.com/library/windows/desktop/aa365150.aspx)  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Verzeichnissteuerung](../c-runtime-library/directory-control.md)   
 [Systemaufrufe](../c-runtime-library/system-calls.md)