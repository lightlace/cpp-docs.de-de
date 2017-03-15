---
title: Prozess- und Umgebungssteuerung | Microsoft-Dokumentation
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
- processes, stopping
- processes, administrative tasks
- parent process
- processes, starting
- environment control routines
- process control routines
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
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
ms.openlocfilehash: d5198dcef7d24d2755c21b90802b19e809c5b8da
ms.lasthandoff: 02/24/2017

---
# <a name="process-and-environment-control"></a>Prozess- und Umgebungssteuerung
Verwenden Sie die Prozesssteuerungsroutinen, um Prozesse aus einem Programm heraus zu starten, zu beenden und zu verwalten. Verwenden Sie die Umgebungssteuerungsroutinen, um Informationen zur Betriebssystemumgebung abzurufen und zu ändern.  
  
### <a name="process-and-environment-control-functions"></a>Funktionen der Prozess- und Umgebungssteuerung  
  
|Routine|Verwendung|.NET Framework-Entsprechung|  
|-------------|---------|-------------------------------|  
|[abort](../c-runtime-library/reference/abort.md)|Bricht einen Prozess an, ohne Puffer zu leeren oder von `atexit` und `_onexit` registrierte Funktionen aufzurufen.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Prüft auf Logikfehler.|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|Makros [_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Entspricht `assert`, ist aber nur in den Debugversionen der Laufzeitbibliotheken verfügbar.|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|Plant Routinen für die Ausführung bei Beendigung des Programms.|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Erstellt einen neuen Thread in einem Windows-Betriebssystemprozess.|[System::Threading::Thread::Start](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Führt `exit`-Beendigungsverfahren aus (z.B. das Leeren der Puffer) und gibt dann die Steuerung an das aufrufende Programm zurück, ohne den Prozess zu beenden.|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|Führt `_exit`-Beendigungsverfahren aus und gibt dann die Steuerung an das aufrufende Programm zurück, ohne den Prozess zu beenden.|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_cwait](../c-runtime-library/reference/cwait.md)|Wartet, bis ein anderer Prozess beendet wird.|[System::Diagnostics::Process::WaitForExit](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Beendet einen Windows-Betriebssystemthread.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|Führt einen neuen Prozess mit einer Argumentliste aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|Führt einen neuen Prozess mit einer Argumentliste und einer angegebenen Umgebung aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Führt einen neuen Prozess mit der Variablen `PATH` und einer Argumentliste aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Führt einen neuen Prozess mit der Variablen `PATH`, einer angegeben Umgebung und einer Argumentliste aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|Führt einen neuen Prozess mit einem Argumentarray aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|Führt einen neuen Prozess mit einem Argumentarray und einer angegebenen Umgebung aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Führt einen neuen Prozess mit der Variablen `PATH` und einem Argumentarray aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|Führt einen neuen Prozess mit der Variablen `PATH`, einer angegeben Umgebung und einem Argumentarray aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|Ruft von `atexit` und `_onexit` registrierte Funktionen auf, leert alle Puffer, schließt alle offenen Dateien und beendet den Prozess.|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|Beendet den Prozess sofort, ohne `atexit` oder `_onexit` aufzurufen oder Puffer zu leeren.|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Ruft den Wert der Umgebungsvariablen ab.|[System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[_getpid](../c-runtime-library/reference/getpid.md)|Ruft die Prozess-ID-Nummer ab.|[System::Diagnostics::Process::Id](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|Stellt die gespeicherte Stapelumgebung wieder her, wird zur Ausführung eines nicht lokalen `goto`-Befehls verwendet.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Plant Routinen für die Ausführung bei Beendigung des Programms, wird zur Kompatibilität mit Microsoft C/C++ Version 7.0 und früher verwendet.|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_pclose](../c-runtime-library/reference/pclose.md)|Wartet auf einen neuen Befehlsprozessor und schließt den Stream auf der zugeordneten Pipe.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)|Druckt eine Fehlermeldung.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_pipe](../c-runtime-library/reference/pipe.md)|Erstellt eine Pipe zum Lesen und Schreiben.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)|Erstellt eine Pipe und führt einen Befehl aus.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md), [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Fügt den Wert einer Umgebungsvariablen hinzu oder ändert ihn.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[raise](../c-runtime-library/reference/raise.md)|Sendet ein Signal an den aufrufenden Prozess.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|Speichert die Stapelumgebung, wird zur Ausführung eines nicht lokalen `goto`-Befehls verwendet.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[signal](../c-runtime-library/reference/signal.md)|Verarbeitet ein Interruptsignal.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Erstellt einen neuen Prozess mit einer angegebenen Argumentliste und führt ihn aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Erstellt einen neuen Prozess mit einer angegebenen Argumentliste und Umgebung und führt ihn aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Erstellt einen neuen Prozess mit der Variablen `PATH` und einer angegebenen Argumentliste und führt ihn aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|Erstellt einen neuen Prozess mit der Variablen `PATH`, einer angegebenen Umgebung und einer Argumentliste und führt ihn aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Erstellt einen neuen Prozess mit einem angegebenen Argumentarray und führt ihn aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Erstellt einen neuen Prozess mit einer angegebenen Umgebung und einem Argumentarray und führt ihn aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Erstellt einen neuen Prozess mit der Variablen `PATH` und einem angegebenen Argumentarray und führt ihn aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|Erstellt einen neuen Prozess mit der Variablen `PATH`, einer angegebenen Umgebung und einem Argumentarray und führt ihn aus.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)|Führt einen Betriebssystembefehl aus.|[System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx), [System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 Im Windows-Betriebssystem entspricht der erzeugte Prozess dem erzeugenden Prozess. Jeder Prozess kann `_cwait` verwenden, um auf einen Prozess zu warten, dessen Prozess-ID bekannt ist.  
  
 Der Unterschied zwischen den Familien `_exec` und `_spawn` ist, dass eine `_spawn`-Funktion die Steuerung vom neuen Prozess an den aufrufenden Prozess zurückgeben kann. In einer `_spawn`-Funktion sind sowohl der aufrufende als auch der neue Prozess im Arbeitsspeicher vorhanden, sofern nicht `_P_OVERLAY` angegeben ist. In einer `_exec`-Funktion überlagert der neue Prozess den aufrufenden Prozess, sodass die Steuerung nur dann an den aufrufenden Prozess zurückgegeben werden kann, wenn beim Versuch, die Ausführung des neuen Prozesses zu starten, ein Fehler auftritt.  
  
 Zu den Unterschieden zwischen den Funktionen in der `_exec`-Familie ebenso wie zwischen denen der `_spawn`-Familie gehören folgende: die Methode zum Suchen der Datei, die als neuer Prozess ausgeführt werden soll; die Form, in der Argumente an den neuen Prozess übergeben werden; die Methode zum Festlegen der Umgebung. Dies wird in der unten stehenden Tabelle erläutert. Verwenden Sie eine Funktion, die eine Argumentliste übergibt, wenn die Anzahl von Argumenten konstant oder zur Kompilierzeit bekannt ist. Verwenden Sie eine Funktion, die einen Zeiger auf ein Array mit den Argumenten übergibt, wenn die Anzahl von Argumenten zur Laufzeit ermittelt werden muss. Die Informationen in der folgenden Tabelle gelten auf für die Breitzeichenentsprechungen der Funktionen `_spawn` und `_exec`.  
  
### <a name="spawn-and-exec-function-families"></a>Funktionsfamilien „_spawn“ und „_exec“  
  
|Funktionen|PATH-Variable zum Suchen der Datei verwenden|Argumentübergabekonvention|Umgebungseinstellungen|  
|---------------|--------------------------------------|----------------------------------|--------------------------|  
|`_execl, _spawnl`|Nein|Liste|Geerbt vom aufrufenden Prozess|  
|`_execle, _spawnle`|Nein|Liste|Zeiger auf Umgebungstabelle für neuen Prozess, der als letztes Argument übergeben wurde|  
|`_execlp, _spawnlp`|Ja|Liste|Geerbt vom aufrufenden Prozess|  
|`_execlpe, _spawnlpe`|Ja|Liste|Zeiger auf Umgebungstabelle für neuen Prozess, der als letztes Argument übergeben wurde|  
|`_execv, _spawnv`|Nein|Array|Geerbt vom aufrufenden Prozess|  
|`_execve, _spawnve`|Nein|Array|Zeiger auf Umgebungstabelle für neuen Prozess, der als letztes Argument übergeben wurde|  
|`_execvp, _spawnvp`|Ja|Array|Geerbt vom aufrufenden Prozess|  
|`_execvpe, _spawnvpe`|Ja|Array|Zeiger auf Umgebungstabelle für neuen Prozess, der als letztes Argument übergeben wurde|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
