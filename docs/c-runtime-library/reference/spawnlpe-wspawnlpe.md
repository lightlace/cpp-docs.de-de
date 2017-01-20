---
title: "_spawnlpe, _wspawnlpe"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_spawnlpe"
  - "_wspawnlpe"
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
  - "spawnlpe"
  - "_wspawnlpe"
  - "_spawnlpe"
  - "wspawnlpe"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_spawnlpe-Funktion"
  - "_wspawnlpe-Funktion"
  - "Prozesserstellung"
  - "Prozesse, Erstellen"
  - "Prozesse, Ausführen der neuen"
  - "spawnlpe-Funktion"
  - "wspawnlpe-Funktion"
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# _spawnlpe, _wspawnlpe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt einen neuen Prozess und führt ihn aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
intptr_t _spawnlpe(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnlpe(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### Parameter  
 `mode`  
 Ausführungsmodus für den aufrufenden Prozess.  
  
 `cmdname`  
 Pfad der auszuführenden Datei.  
  
 `arg0, arg1, ... argn`  
 Liste von Zeigern zu Argumenten.  Das `arg0`\-Argument ist normalerweise ein Zeiger auf `cmdname`.  Die Argumente `arg1` bis `argn` sind Zeiger auf die Zeichenfolgen, welche die neue Argumentliste bilden.  Nach `argn` muss ein `NULL`\-Zeiger stehen, mit dem das Ende der Argumentliste markiert wird.  
  
 `envp`  
 Array von Zeigern zu Umgebungseinstellungen.  
  
## Rückgabewert  
 Der Rückgabewert eines synchronen `_spawnlpe` oder `_wspawnlpe` \(`_P_WAIT` angegeben für `mode`\) ist der Beendigungsstatus des neuen Prozesses.  Der Rückgabewert eines asynchronen `_spawnlpe` oder `_wspawnlpe` \(`_P_NOWAIT` oder `_P_NOWAITO` angegeben für `mode`\) ist das Prozesshandle.  Der Beendigungsstatus ist 0, wenn der Prozess ordnungsgemäß beendet wurde.  Sie können den Beendigungsstatus auf einen Wert ungleich 0 einstellen, wenn der gestartete Prozess die `exit`\-Routine speziell mit einem Argument ungleich 0 aufruft.  Wenn der neue Prozess nicht explizit einen positiven Beendigungsstatus eingestellt hat, weist ein positiver Beendigungsstatus auf eine abnormale Beendigung aufgrund eines Abbruchs oder einer Unterbrechung hin.  Ein Rückgabewert von \- 1 gibt an, dass ein Fehler vorliegt \(der neue Prozess wird nicht gestartet\).  In diesem Fall wird `errno` auf einen der folgenden Werte festgelegt.  
  
 `E2BIG`  
 Argumentliste umfasst mehr als 1024 Byte.  
  
 `EINVAL`  
 `mode`\-Argument ist ungültig.  
  
 `ENOENT`  
 Datei oder Pfad nicht gefunden.  
  
 `ENOEXEC`  
 Die angegebene Datei ist nicht ausführbar oder verfügt über ein für eine ausführbare Datei ungültiges Format.  
  
 `ENOMEM`  
 Es ist nicht genügend Arbeitsspeicher verfügbar, um den neuen Prozess auszuführen.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Jede dieser Funktionen erstellt einen neuen Prozess und führt diesen aus, übergibt jedes Befehlszeilenargument als separaten Parameter und übergibt außerdem ein Array von Zeigern auf die Umgebungseinstellungen.  Diese Funktionen suchen die auszuführende Datei mithilfe der `PATH`\-Umgebungsvariable.  
  
 Diese Funktionen überprüfen ihre Parameter.  Wenn entweder `cmdname` oder `arg0` eine leere Zeichenfolge oder ein NULL\-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben – 1 zurück.  Es wird kein neuer Prozess erzeugt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_spawnlpe`|\<process.h\>|  
|`_wspawnlpe`|\<stdio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Siehe das Beispiel in [\_spawn\- und \_wspawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [\_spawn\- und \_wspawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec\- und \_wexec\-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)