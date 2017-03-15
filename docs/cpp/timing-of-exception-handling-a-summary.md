---
title: "Zeitliche Steuerung der Ausnahmebehandlung: Eine Zusammenfassung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausnahmebehandlung, Planen"
  - "Handler, Reihenfolge der Ausführung"
  - "Reihenfolge"
  - "Reihenfolge, der Handler"
  - "SETJMP.H"
  - "SETJMPEX.H"
  - "Strukturierte Ausnahmebehandlung, Planen"
  - "Beendigungshandler, Planen"
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Zeitliche Steuerung der Ausnahmebehandlung: Eine Zusammenfassung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Beendigungshandler wird unabhängig davon ausgeführt, wie der `__try`\-Anweisungsblock beendet wird.  Zu den Ursachen gehören das Herausspringen aus dem `__try`\-Block, eine `longjmp`\-Anweisung, die die Steuerung aus dem Block überträgt, und das Entladen des Stapels aufgrund einer Ausnahmebehandlung.  
  
> [!NOTE]
>  Visual C\+\+ unterstützt zwei Formen der Anweisungen `setjmp` und `longjmp`.  Die schnelle Version umgeht die Abbruchbehandlung, ist jedoch effizienter.  Um diese Version zu verwenden, schließen Sie die SETJMP.H\-Datei ein.  Die andere Version unterstützt die Abbruchbehandlung, wie im vorherigen Abschnitt beschrieben.  Um diese Version zu verwenden, schließen Sie die SETJMPEX.H\-Datei ein.  Die Leistungssteigerung der schnellen Version hängt von der Hardwarekonfiguration ab.  
  
 Das Betriebssystem führt alle Abbruchbehandlungen in der richtigen Reihenfolge aus, bevor ein anderer Code ausgeführt werden kann, einschließlich des Texts eines Ausnahmehandlers.  
  
 Wenn die Ursache für die Unterbrechung eine Ausnahme ist, muss das System erst den Filterteil einer oder mehrerer Ausnahmehandler ausführen, bevor entschieden wird, was beendet werden soll.  Die Reihenfolge der Ereignisse lautet:  
  
1.  Eine Ausnahme wird ausgelöst.  
  
2.  Das System untersucht die Hierarchie der aktiven Ereignishandler und führt den Filter des Handlers mit der höchsten Rangstufe aus. Hierbei handelt es sich um den Ausnahmehandler, der im Hinblick auf Blöcke und Funktionsaufrufe zuletzt installiert wurde und am tiefsten geschachtelt ist.  
  
3.  Wenn dieser Filter die Steuerung übergibt \(0 zurückgibt\), wird der Prozess fortgesetzt, bis ein Filter gefunden wird, der die Steuerung nicht übergibt.  
  
4.  Wenn dieser Filter –1 zurückgibt, wird die Ausführung dort fortgesetzt, wo die Ausnahme ausgelöst wurde, und es findet keine Beendigung statt.  
  
5.  Wenn der Filter 1 zurückgibt, werden folgende Ereignisse ausgelöst:  
  
    -   Das System entlädt den Stapel und löscht alle Stapelrahmen zwischen dem gerade ausgeführten Code \(bei dem die Ausnahme ausgelöst wurde\) und dem Stapelrahmen, der den Ausnahmehandler enthält, der nun die Steuerung übernimmt.  
  
    -   Beim Entladen des Stapels wird jeder Beendigungshandler im Stapel ausgeführt.  
  
    -   Der Ausnahmehandler selbst wird ausgeführt.  
  
    -   Die Steuerung wird nach dem Ende des Ausnahmehandlers an die Codezeile übergeben.  
  
## Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)