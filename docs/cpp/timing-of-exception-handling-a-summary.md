---
title: 'Zeitliche Steuerung der Ausnahmebehandlung: eine Zusammenfassung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 446925b6e00f4771229357effee0707af3fae52a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422175"
---
# <a name="timing-of-exception-handling-a-summary"></a>Zeitliche Steuerung der Ausnahmebehandlung: Eine Zusammenfassung
Ein Beendigungshandler wird unabhängig davon ausgeführt, wie der `__try`-Anweisungsblock beendet wird. Zu den Ursachen gehören das Herausspringen aus dem `__try`-Block, eine `longjmp`-Anweisung, die die Steuerung aus dem Block überträgt, und das Entladen des Stapels aufgrund einer Ausnahmebehandlung.  
  
> [!NOTE]
>  Visual C++ unterstützt zwei Formen der Anweisungen `setjmp` und `longjmp`. Die schnelle Version umgeht die Abbruchbehandlung, ist jedoch effizienter. Um diese Version verwenden möchten, schließen Sie die Datei \<setjmp.h >. Die andere Version unterstützt die Abbruchbehandlung, wie im vorherigen Abschnitt beschrieben. Um diese Version verwenden möchten, schließen Sie die Datei \<setjmpex.h >. Die Leistungssteigerung der schnellen Version hängt von der Hardwarekonfiguration ab.  
  
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