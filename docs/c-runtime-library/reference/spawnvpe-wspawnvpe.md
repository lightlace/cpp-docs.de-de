---
title: "_spawnvpe, _wspawnvpe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_spawnvpe"
  - "_wspawnvpe"
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
  - "_spawnvpe"
  - "wspawnvpe"
  - "spawnvpe"
  - "_wspawnvpe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_spawnvpe-Funktion"
  - "_wspawnvpe-Funktion"
  - "Prozesserstellung"
  - "Prozesse, Erstellen"
  - "Prozesse, Ausführen der neuen"
  - "spawnvpe-Funktion"
  - "wspawnvpe-Funktion"
ms.assetid: 3db6394e-a955-4837-97a1-fab1db1e6092
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _spawnvpe, _wspawnvpe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt einen neuen Prozess und führt ihn aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
intptr_t _spawnvpe(  
   int mode,  
   const char *cmdname,  
   const char *const *argv,  
   const char *const *envp   
);  
intptr_t _wspawnvpe(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv,  
   const wchar_t *const *envp   
);  
```  
  
#### Parameter  
 `mode`  
 Ausführungsmodus für einen aufrufenden Prozess  
  
 `cmdname`  
 Pfad der auszuführenden Datei  
  
 `argv`  
 Array von Zeigern zu Argumenten.  Das `argv`\[0\]\-Argument ist gewöhnlich ein Zeiger auf einen Pfad im Echtzeitmodus oder auf den Programmnamen im geschützten Modus und `argv`\[1\] bis `argv`\[`n`\] sind Zeiger auf die Zeichenfolgen, die die neue Argumentliste bilden.  Das Argument `argv`\[`n` \+1\] muss ein `NULL`\-Zeiger sein, um das Ende der Argumentliste zu markieren.  
  
 `envp`  
 Array von Zeigern zu Umgebungseinstellungen  
  
## Rückgabewert  
 Der Rückgabewert eines synchronen `_spawnvpe` oder `_wspawnvpe` \(`_P_WAIT` angegeben für `mode`\) ist der Beendigungsstatus des neuen Prozesses.  Der Rückgabewert eines asynchronen `_spawnvpe` oder `_wspawnvpe` \(`_P_NOWAIT` oder `_P_NOWAITO` angegeben für `mode`\) ist das Prozesshandle.  Der Beendigungsstatus ist 0, wenn der Prozess ordnungsgemäß beendet wurde.  Sie können den Beendigungsstatus auf einen Wert ungleich 0 einstellen, wenn der gestartete Prozess speziell die `exit`\-Routine mit einem Argument ungleich 0 aufruft.  Wenn der neue Prozess nicht explizit einen positiven Beendigungsstatus eingestellt hat, weist ein positiver Beendigungsstatus auf eine abnormale Beendigung mit einem Abbruch oder einer Unterbrechung hin.  Ein Rückgabewert von \- 1 gibt an, dass ein Fehler vorliegt \(der neue Prozess wird nicht gestartet\).  In diesem Fall wird `errno` auf einen der folgenden Werte festgelegt:  
  
 `E2BIG`  
 Argumentliste umfasst mehr als 1024 Byte  
  
 `EINVAL`  
 `mode`\-Argument ist ungültig  
  
 `ENOENT`  
 Datei oder Pfad nicht gefunden  
  
 `ENOEXEC`  
 Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei  
  
 `ENOMEM`  
 Es ist nicht genügend Arbeitsspeicher verfügbar, um den neuen Prozess auszuführen  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Jede dieser Funktionen erstellt einen neuen Prozess, führt diesen aus und übergibt ein Array von Zeigern auf Befehlszeilenargumente und ein Array von Zeigern auf die Umgebungseinstellungen.  Diese Funktionen suchen die auszuführende Datei mithilfe der `PATH`\-Umgebungsvariable.  
  
 Diese Funktionen überprüfen ihre Parameter.  Wenn `cmdname` oder `argv` ein NULL\-Zeiger ist oder `argv` auf einen NULL\-Zeiger zeigt oder `argv[0]` eine leere Zeichenfolge ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben – 1 zurück.  Es wird kein neuer Prozess erzeugt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_spawnvpe`|\<stdio.h\> oder \<process.h\>|  
|`_wspawnvpe`|\<stdio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Siehe das Beispiel in [\_spawn\-, \_wspawn\-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## Siehe auch  
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec\- und \_wexec\-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)