---
title: "Prozess- und Umgebungssteuerung | Microsoft Docs"
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
  - "Umgebungssteuerungsroutinen"
  - "Übergeordneter Prozess"
  - "Prozesssteuerroutinen"
  - "Prozesse, Verwaltungsaufgaben"
  - "Prozesse, Starten"
  - "Prozesse, Anhalten"
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Prozess- und Umgebungssteuerung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie die Routinen Prozesslenkung, um Prozesse aus ein Programm starten, zu beenden und zu verwalten.  Verwenden Sie die UmgebungSteuerelementroutinen, um zu und Änderungsinformationen über der Betriebssystemumgebung.  
  
### Prozess\- Umgebungs\-Kontrollfunktionen  
  
|Routine|Verwendung|.NET Framework\-Entsprechung|  
|-------------|----------------|----------------------------------|  
|[Abbruch](../c-runtime-library/reference/abort.md)|Abbruchsprozess, ohne Puffer oder aufrufende Funktionen zu leeren, registrierte durch `atexit` und `_onexit`|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Test für logischen Fehler|[\<caps:sentence id\="tgt14" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|Makros [\_ASSERT, \_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Wie auch `assert`, jedoch nur verfügbar in den Debugversionen der Laufzeitbibliotheken|[\<caps:sentence id\="tgt17" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|Zeitplanroutinen für Ausführung an der dass|[\<caps:sentence id\="tgt20" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_beginthread\-Funktion, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Erstellen Sie einen neuen Thread auf ein Windows\-Betriebssystemprozess|[\<caps:sentence id\="tgt23" sentenceid\="221e38ecc6535bce91af4e1a19f464d1" class\="tgtSentence"\>System::Threading::Thread::Start\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[\_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Führen Sie `exit` Beendigungsprozeduren \(z Leeren von Puffern\) aus, und geben Sie Kontrolle an das aufrufende Programm zurückgegeben, ohne Prozess zu beenden|[\<caps:sentence id\="tgt26" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_c\_exit](../c-runtime-library/reference/cexit-c-exit.md)|Führen Sie `_exit` Beendigungsprozeduren aus, und geben Sie Kontrolle an das aufrufende Programm zurückgegeben, ohne Prozess zu beenden|[\<caps:sentence id\="tgt29" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_cwait](../c-runtime-library/reference/cwait.md)|Warten Sie, bis ein anderer Prozess beendet wird|[\<caps:sentence id\="tgt32" sentenceid\="d9c88c429eaacaa9f37d91d29bc6504e" class\="tgtSentence"\>System::Diagnostics::Process::WaitForExit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[\_endthread\-Funktion, \_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Beenden eines Windows\-Betriebssystemthread|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_execl, \_wexecl](../c-runtime-library/reference/execl-wexecl.md)|Führen Sie neuen Prozess mit Argumentliste aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execle, \_wexecle](../c-runtime-library/reference/execle-wexecle.md)|Führen Sie neuen Prozess mit Argumentliste und bestimmter Umgebungen aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlp, \_wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Führen Sie neuen Prozess mit `PATH` und \-Argumentliste Variable aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlpe, \_wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Führen Sie neuen Prozess mit `PATH`\-Variable aus, Umgebung und Argumentliste angegeben|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execv, \_wexecv](../c-runtime-library/reference/execv-wexecv.md)|Führen Sie neuen Prozess mit Argumentarray aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execve, \_wexecve](../c-runtime-library/reference/execve-wexecve.md)|Führen Sie neuen Prozess mit Argumentarray und bestimmter Umgebungen aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvp, \_wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Führen Sie neuen Prozess mit `PATH` und \-Argumentarrays Variable aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvpe, \_wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|Führen Sie neuen Prozess mit `PATH`\-Variable aus, Umgebung und Argumentarray angegeben|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|Rufen Sie Funktionen registriert durch `atexit` und `_onexit` auf, leeren Sie alle Puffer, schließen Sie alle geöffneten Dateien, und beenden Sie Prozess|[\<caps:sentence id\="tgt64" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[\_exit](../c-runtime-library/reference/exit-exit-exit.md)|Beenden Sie Prozess sofort, ohne `atexit` oder `_onexit` aufrufen oder Puffer zu leeren|[\<caps:sentence id\="tgt67" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Rufen Sie Wert der Umgebungsvariablen von ab|[\<caps:sentence id\="tgt70" sentenceid\="795988b9277d74ea3b722ecd42dcb29d" class\="tgtSentence"\>System::Environment::GetEnvironmentVariable\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[\_getpid](../c-runtime-library/reference/getpid.md)|Rufen Sie Prozess\-ID\-Nummer ab|[\<caps:sentence id\="tgt73" sentenceid\="745b82c461dc74b15540e9622f7cd7bd" class\="tgtSentence"\>System::Diagnostics::Process::Id\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|Erstellen Sie gespeicherte Stapelumgebung wiederherstellen; verwenden Sie sie, um nicht lokalen `goto` auszuführen|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Zeitplanroutinen für Ausführung an der dass; Verwendung für Kompatibilität mit Version 7.0 Microsoft C\/C\+\+ und früher|[\<caps:sentence id\="tgt81" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_pclose](../c-runtime-library/reference/pclose.md)|Warten Sie neuen Befehlsprozessor und schließen Sie Stream für zugehörige Pipe|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[perror, \_wperror](../c-runtime-library/reference/perror-wperror.md)|Drucksfehlermeldung|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_pipe](../c-runtime-library/reference/pipe.md)|Erstellen Sie Pipe zum Lesen und Schreiben erstellt|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md)|Erstellen Sie Pipe und führen Sie folgenden Befehl aus|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md), [\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Hinzufügen oder Ändern Sie Wert der Umgebungsvariablen|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[raise](../c-runtime-library/reference/raise.md)|Senden von Signal für den aufrufenden Prozesses|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|Speichern Sie Stapelumgebung; Verwendung, nicht lokalen `goto` auszuführen|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[Signal](../c-runtime-library/reference/signal.md)|Handle\-Unterbrechungssignal|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_spawnl, \_wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Erstellen und Ausführen neuen Prozess mit angegebener Argumentliste aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnle, \_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Erstellen und Ausführen neuen Prozess mit angegebener Argumentliste und Umgebungen aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlp, \_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Erstellen und Ausführen neuen Prozess mit `PATH` und der angegebenen Variable Argumentliste aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlpe, \_wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|Erstellen und Ausführen neuen Prozess mit `PATH`\-Variable, der angegebenen Umgebung und der Argumentliste aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnv, \_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Erstellen und Ausführen neuen Prozess mit angegebenem Argumentarray aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnve, \_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Erstellen und Ausführen neuen Prozess mit angegebener Umgebung und Argumentarray aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvp, \_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Erstellen und Ausführen neuen Prozess mit `PATH` angegebenen Variable und des Argumentarrays aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvpe, \_wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|Erstellen und Ausführen neuen Prozess mit `PATH`\-Variable, der angegebenen Umgebung und des Argumentarrays aus|[System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[System, \_wsystem](../c-runtime-library/reference/system-wsystem.md)|Führen Sie Betriebssystembefehl aus|[System::Diagnostics::ProcessStartInfo\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx), [System::Diagnostics::Process\-Klasse](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 Im Windows\-Betriebssystem ist der generierte Prozess z erzeugenden Prozess entsprechend.  Jeder Prozess kann die `_cwait` verwenden, um auf einen anderen Prozess zu warten, für den die Prozess\-ID bezeichnet.  
  
 Der Unterschied zwischen `_exec` und den `_spawn` Familien ist, dass eine `_spawn`\-Funktion Steuerelement vom neuen Prozess zum aufrufenden Prozesses zurückgeben kann.  In einer `_spawn`\-Funktion sind der aufrufende Prozess und der neue Prozess im Arbeitsspeicher vorhanden, es sei denn, `_P_OVERLAY` angegeben wird.  In einer `_exec`\-Funktion der neue Prozess der aufrufende Prozess, sodass Steuerelement nicht dem aufrufenden Prozesses zurückkehren, es sei denn, dass ein Fehler im Test, Ausführung des neuen Vorgangs zu starten auftritt.  
  
 Die Unterschiede zwischen den Funktionen der `_exec` Familie sowie unter denen in der `_spawn` \- Familie, beziehen die Methode Lokalisierens der als mit ein neue Prozess, der das Formular, in der Argumente den neuen Prozess übergeben werden, und die Methode des Festlegens ausgeführt werden Datei, der Umgebung, wie in der folgenden Tabelle.  Verwenden Sie eine Funktion, der eine Argumentliste werden, wenn die Anzahl von Argumenten konstant ist oder zur Kompilierungszeit bekannt.  Verwenden Sie eine Funktion, die einen Zeiger auf ein Array übergibt, das die Argumente enthält, wenn die Anzahl der Argumente zur Laufzeit bestimmt werden soll.  Die Informationen in der folgenden Tabelle gelten auch für die Breitzeichenentsprechungen der Funktionen `_spawn` und `_exec` zu.  
  
### \_spawn und \_exec Funktions\-Familien  
  
|Funktionen|Verwendung PFADvariable, um die Datei zu suchen|Argumentübergabekonvention|Umgebungseinstellungen|  
|----------------|-----------------------------------------------------|--------------------------------|----------------------------|  
|`_execl, _spawnl`|nein|List|Diese vom aufrufenden Prozesses|  
|`_execle, _spawnle`|nein|List|Zeiger auf Umgebungstabelle für neuen Prozess wurde als zuletzt Argument|  
|`_execlp, _spawnlp`|ja|List|Diese vom aufrufenden Prozesses|  
|`_execlpe, _spawnlpe`|ja|List|Zeiger auf Umgebungstabelle für neuen Prozess wurde als zuletzt Argument|  
|`_execv, _spawnv`|nein|Array|Diese vom aufrufenden Prozesses|  
|`_execve, _spawnve`|nein|Array|Zeiger auf Umgebungstabelle für neuen Prozess wurde als zuletzt Argument|  
|`_execvp, _spawnvp`|ja|Array|Diese vom aufrufenden Prozesses|  
|`_execvpe, _spawnvpe`|ja|Array|Zeiger auf Umgebungstabelle für neuen Prozess wurde als zuletzt Argument|  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)