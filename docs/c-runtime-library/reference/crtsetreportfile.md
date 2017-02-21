---
title: "_CrtSetReportFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportFile"
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
apitype: "DLLExport"
f1_keywords: 
  - "CrtSetReportFile"
  - "_CrtSetReportFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtSetReportFile-Funktion"
  - "_CrtSetReportFile-Funktion"
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _CrtSetReportFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) verwendet haben, um `_CRTDBG_MODE_FILE` anzugeben, können Sie das Dateihandle angeben, um den Meldungstext zu empfangen.  `_CrtSetReportFile` wird auch von [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) verwendet, um das Ziel des Texts anzugeben \(nur Debugversion\).  
  
## Syntax  
  
```  
_HFILE _CrtSetReportFile(   
   int reportType,  
   _HFILE reportFile   
);  
```  
  
#### Parameter  
 `reportType`  
 Berichtstyp: `_CRT_WARN`, `_CRT_ERROR` und `_CRT_ASSERT`.  
  
 `reportFile`  
 Neue Berichtsdatei für `reportType`.  
  
## Rückgabewert  
 Nach erfolgreichem Abschluss gibt `_CrtSetReportFile` die vorherige Berichtsdatei zurück, die für den Berichtstyp definiert ist, der in `reportType` angegeben wird.  Wenn ein ungültiger Wert für `reportType` übergeben wird, ruft diese Funktion den Handler für ungültigen Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `_CRTDBG_HFILE_ERROR` zurück.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 `_CrtSetReportFile` wird mit der [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)\-Funktion verwendet, um das Ziel oder die Ziele für einen angegebenen Berichtstyp zu definieren, der von `_CrtDbgReport` generiert wird.  Wenn `_CrtSetReportMode` aufgerufen wurde, um den `_CRTDBG_MODE_FILE`\-Berichtsmodus für einen bestimmten Berichtstyp zuzuweisen, dann sollte `_CrtSetReportFile` aufgerufen werden, um die bestimmte Datei oder den Stream festzulegen, der als Ziel verwendet wird.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetReportFile` während der Vorverarbeitung entfernt.  
  
 In der folgenden Tabelle wird eine Liste der verfügbaren Optionen für `reportFile` sowie das resultierende Verhalten von `_CrtDbgReport` gezeigt.  Diese Optionen werden als Bitflags in Crtdbg.h definiert.  
  
 `file handle`  
 Ein Handle für die Datei, die das Ziel der Meldungen ist.  Es wird nicht versucht, die Gültigkeit des Handles zu überprüfen.  Sie müssen das Handle für die Datei öffnen und schließen.  Beispiel:  
  
```  
HANDLE hLogFile;  
hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,   
   FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,   
   FILE_ATTRIBUTE_NORMAL, NULL);  
_CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_WARN, hLogFile);  
  
_RPT0(_CRT_WARN,"file message\n");  
CloseHandle(hLogFile);  
```  
  
 `_CRTDBG_FILE_STDERR`  
 Schreibt Meldungen an `stderr`, die wie folgt umgeleitet werden können:  
  
```  
freopen( "c:\\log2.txt", "w", stderr);  
_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);  
  
_RPT0(_CRT_ERROR,"1st message\n");  
```  
  
 `_CRTDBG_FILE_STDOUT`  
 Schreibt Meldungen für `stdout`, die umgeleitet werden können.  
  
 `_CRTDBG_REPORT_FILE`  
 Gibt den aktuellen Berichtsmodus zurück.  
  
 Die Berichtsdatei, die von jedem Berichtstyp verwendet wird, kann separat gesteuert werden.  So kann beispielsweise angegeben werden, dass ein `reportType` von `_CRT_ERROR` an `stderr` gemeldet wird, während ein `reportType` von `_CRT_ASSERT` an ein benutzerdefiniertes Dateihandle oder einen Stream gemeldet wird.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_CrtSetReportFile`|\<crtdbg.h\>|\<errno.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
 **Bibliotheken:** nur Debugversionen von [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)