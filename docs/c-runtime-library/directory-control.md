---
title: "Verzeichnissteuerung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [C++], Verzeichnis"
  - "Verzeichnissteuerroutinen"
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Verzeichnissteuerung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Routinen greifen zu, ändern und bringen auf Informationen über die Verzeichnisstruktur ein.  
  
### Verzeichnis\-Steuerelement\-Routinen  
  
|Routine|Verwendung|.NET Framework\-Entsprechung|  
|-------------|----------------|----------------------------------|  
|[\_chdir, \_wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Änderungsstromarbeitsverzeichnis|[\<caps:sentence id\="tgt8" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_chdrive](../c-runtime-library/reference/chdrive.md)|Änderungsaktuelles laufwerk|[\<caps:sentence id\="tgt11" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getcwd, \_wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Rufen Sie aktuelle Arbeitsverzeichnis für Standardlaufwerk ab|[\<caps:sentence id\="tgt14" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdcwd, \_wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Rufen Sie aktuelle Arbeitsverzeichnis für einen angegebenen Laufwerk ab|[\<caps:sentence id\="tgt16" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Füllt eine Struktur `_diskfree_t` mit Informationen über ein Laufwerk auf.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_getdrive](../c-runtime-library/reference/getdrive.md)|Rufen Sie aktuelle \(Standard\) Laufwerk ab|[\<caps:sentence id\="tgt23" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdrives](../c-runtime-library/reference/getdrives.md)|Gibt eine Bitmaske zurück, die die derzeit verfügbaren Laufwerke darstellt.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_mkdir, \_wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Ausführen neues Verzeichnis|[System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx), [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)|  
|[\_rmdir, \_wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Verzeichnis entfernen|[\<caps:sentence id\="tgt32" sentenceid\="de5c5e84e86fdd3cd99296d3b2518f57" class\="tgtSentence"\>System::IO::Directory::Delete\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)|  
|[\_searchenv, \_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [\_searchenv\_s, \_wsearchenv\_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Suche für angegebene Datei auf angegebenen Pfaden|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Dateibehandlung](../c-runtime-library/file-handling.md)   
 [Systemaufrufe](../c-runtime-library/system-calls.md)