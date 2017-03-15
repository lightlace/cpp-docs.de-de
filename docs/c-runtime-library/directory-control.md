---
title: Verzeichnissteuerung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 49084f97470965f2b3d8fec627f0d0c92f4ec522
ms.lasthandoff: 02/24/2017

---
# <a name="directory-control"></a>Verzeichnissteuerung
Diese Routinen greifen auf die Verzeichnisstruktur zu, ändern sie und rufen Informationen dazu ab.  
  
### <a name="directory-control-routines"></a>Routinen für die Verzeichnissteuerung  
  
|Routine|Verwendung|.NET Framework-Entsprechung|  
|-------------|---------|-------------------------------|  
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Ändert das aktuelle Arbeitsverzeichnis.|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Ändert das aktuelle Laufwerk.|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Ruft das aktuelle Arbeitsverzeichnis für das Standardlaufwerk ab.|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Ruft das aktuelle Arbeitsverzeichnis für das angegebene Laufwerk ab.|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Füllt eine `_diskfree_t`-Struktur mit Informationen über ein Laufwerk auf.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Ruft das aktuelle (standardmäßige) Laufwerk ab.|[System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Gibt eine Bitmaske zurück, die die aktuell verfügbaren Laufwerke darstellt.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Erstellt ein neues Verzeichnis.|[System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx), [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)|  
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Verzeichnis entfernen|[System::IO::Directory::Delete](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)|  
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Sucht nach der angegebenen Datei in den angegebenen Pfaden.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Dateibehandlung](../c-runtime-library/file-handling.md)   
 [Systemaufrufe](../c-runtime-library/system-calls.md)
