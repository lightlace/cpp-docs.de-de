---
title: 'Zeitliche Steuerung der Ausnahmebehandlung: eine Zusammenfassung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- sequence
- sequence, of handlers
- exception handling, timing
- SETJMPEX.H
- termination handlers, timing
- SETJMP.H
- handlers, order of exception
- structured exception handling, timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0ba1075095381229667c7164aa7de7f3e4537486
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="timing-of-exception-handling-a-summary"></a>Zeitliche Steuerung der Ausnahmebehandlung: Eine Zusammenfassung
Ein Beendigungshandler wird unabhängig davon ausgeführt, wie der `__try`-Anweisungsblock beendet wird. Zu den Ursachen gehören das Herausspringen aus dem `__try`-Block, eine `longjmp`-Anweisung, die die Steuerung aus dem Block überträgt, und das Entladen des Stapels aufgrund einer Ausnahmebehandlung.  
  
> [!NOTE]
>  Visual C++ unterstützt zwei Formen der Anweisungen `setjmp` und `longjmp`. Die schnelle Version umgeht die Abbruchbehandlung, ist jedoch effizienter. Um diese Version zu verwenden, schließen Sie die SETJMP.H-Datei ein. Die andere Version unterstützt die Abbruchbehandlung, wie im vorherigen Abschnitt beschrieben. Um diese Version zu verwenden, schließen Sie die SETJMPEX.H-Datei ein. Die Leistungssteigerung der schnellen Version hängt von der Hardwarekonfiguration ab.  
  
 Das Betriebssystem führt alle Abbruchbehandlungen in der richtigen Reihenfolge aus, bevor ein anderer Code ausgeführt werden kann, einschließlich des Texts eines Ausnahmehandlers.  
  
 Wenn die Ursache für die Unterbrechung eine Ausnahme ist, muss das System erst den Filterteil einer oder mehrerer Ausnahmehandler ausführen, bevor entschieden wird, was beendet werden soll. Die Reihenfolge der Ereignisse lautet:  
  
1.  Eine Ausnahme wird ausgelöst.  
  
2.  Das System untersucht die Hierarchie der aktiven Ereignishandler und führt den Filter des Handlers mit der höchsten Rangstufe aus. Hierbei handelt es sich um den Ausnahmehandler, der im Hinblick auf Blöcke und Funktionsaufrufe zuletzt installiert wurde und am tiefsten geschachtelt ist.  
  
3.  Wenn dieser Filter die Steuerung übergibt (0 zurückgibt), wird der Prozess fortgesetzt, bis ein Filter gefunden wird, der die Steuerung nicht übergibt.  
  
4.  Wenn dieser Filter – 1 zurückgibt, wird die Ausführung fortgesetzt, in dem die Ausnahme ausgelöst wurde, und findet keine Beendigung statt.  
  
5.  Wenn der Filter 1 zurückgibt, werden folgende Ereignisse ausgelöst:  
  
    -   Das System entlädt den Stapel und löscht alle Stapelrahmen zwischen dem gerade ausgeführten Code (bei dem die Ausnahme ausgelöst wurde) und dem Stapelrahmen, der den Ausnahmehandler enthält, der nun die Steuerung übernimmt.  
  
    -   Beim Entladen des Stapels wird jeder Beendigungshandler im Stapel ausgeführt.  
  
    -   Der Ausnahmehandler selbst wird ausgeführt.  
  
    -   Die Steuerung wird nach dem Ende des Ausnahmehandlers an die Codezeile übergeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
