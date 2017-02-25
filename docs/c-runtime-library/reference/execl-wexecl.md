---
title: "_execl, _wexecl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_execl"
  - "_wexecl"
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
  - "api-ms-win-crt-process-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_execl"
  - "_wexecl"
  - "wexecl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_execl-Funktion"
  - "_wexecl-Funktion"
  - "Excel-Funktion"
  - "wexecl-Funktion"
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _execl, _wexecl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lädt neue untergeordnete Prozesse und führt sie aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
intptr_t _execl(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexecl(  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### Parameter  
 `cmdname`  
 Pfad der auszuführenden Datei.  
  
 `arg0`, `...``argn`  
 Liste von Zeigern zu den Parametern.  
  
## Rückgabewert  
 Bei Erfolg kehren diese Funktionen nicht zum aufrufenden Prozess zurück.  Ein Rückgabewert von \- 1 gibt an, dass ein Fehler vorliegt; dann wird die globale Variable `errno` festgelegt.  
  
|errno\-Wert|**Beschreibung**|  
|-----------------|----------------------|  
|`E2BIG`|Für die Argumente und die Umgebungseinstellungen werden mehr als 32 KB Speicherplatz benötigt.|  
|`EACCES`|Für die angegebene Datei ist eine Sperr\- oder Freigabeverletzung aufgetreten.|  
|`EINVAL`|Ungültiger Parameter \(mindestens ein Parameter ist ein NULL\-Zeiger oder eine leere Zeichenfolge\).|  
|`EMFILE`|Zu viele Dateien geöffnet \(die angegebene Datei muss geöffnet werden, damit festgestellt werden kann, ob sie ausführbar ist\).|  
|`ENOENT`|Die Datei oder der Pfad wurde nicht gefunden.|  
|`ENOEXEC`|Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei.|  
|`ENOMEM`|Es ist nicht genügend Arbeitsspeicher, um den neuen Prozess auszuführen; der verfügbare Arbeitsspeicher ist beschädigt; oder es ist ein ungültiger Block vorhanden, was darauf hinweist, dass der aufrufende Prozess nicht ordnungsgemäß zugeordnet wurde.|  
  
## Hinweise  
 Jede dieser Funktionen lädt einen neuen Prozess und führt ihn aus. Jedes Befehlszeilenargument wird dabei als separater Parameter übergeben.  Das erste Argument ist der Name des Befehls oder der ausführbaren Datei. Das zweite Argument muss das gleiche wie das erste sein.  Es wird im ausgeführten Prozess zu `argv[0]`.  Das dritte Argument `argv[1]` ist das erste Argument des ausgeführten Prozesses.  
  
 Die `_execl`\-Funktionen überprüfen ihre Parameter.  Wenn entweder `cmdname` oder `arg0` ein NULL\-Zeiger oder leere Zeichenfolge ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben – 1 zurück.  Es wird kein neuer Prozess ausgeführt.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|Optionaler Header|  
|--------------|---------------------------|-----------------------|  
|`_execl`|\<process.h\>|\<errno.h\>|  
|`_wexecl`|\<process.h\> oder \<wchar.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Siehe das Beispiel in [\_exec\-, \_wexec\-Funktionen](../../c-runtime-library/exec-wexec-functions.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec\- und \_wexec\-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn\- und \_wspawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)