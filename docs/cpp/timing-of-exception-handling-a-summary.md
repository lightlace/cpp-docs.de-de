---
title: 'Timing of exception handling: A summary'
ms.date: 05/07/2019
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
ms.openlocfilehash: 870606c3661df3654581760214e48ef2bdfb1987
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246334"
---
# <a name="timing-of-exception-handling-a-summary"></a>Timing of exception handling: A summary

A termination handler is executed no matter how the **__try** statement block is terminated. Causes include jumping out of the **__try** block, a `longjmp` statement that transfers control out of the block, and unwinding the stack due to exception handling.

> [!NOTE]
>  The Microsoft C++ compiler supports two forms of the `setjmp` and `longjmp` statements. Die schnelle Version umgeht die Abbruchbehandlung, ist jedoch effizienter. To use this version, include the file \<setjmp.h>. Die andere Version unterstützt die Abbruchbehandlung, wie im vorherigen Abschnitt beschrieben. To use this version, include the file \<setjmpex.h>. Die Leistungssteigerung der schnellen Version hängt von der Hardwarekonfiguration ab.

Das Betriebssystem führt alle Abbruchbehandlungen in der richtigen Reihenfolge aus, bevor ein anderer Code ausgeführt werden kann, einschließlich des Texts eines Ausnahmehandlers.

Wenn die Ursache für die Unterbrechung eine Ausnahme ist, muss das System erst den Filterteil einer oder mehrerer Ausnahmehandler ausführen, bevor entschieden wird, was beendet werden soll. Die Reihenfolge der Ereignisse lautet:

1. Eine Ausnahme wird ausgelöst.

1. Das System untersucht die Hierarchie der aktiven Ereignishandler und führt den Filter des Handlers mit der höchsten Rangstufe aus. Hierbei handelt es sich um den Ausnahmehandler, der im Hinblick auf Blöcke und Funktionsaufrufe zuletzt installiert wurde und am tiefsten geschachtelt ist.

1. Wenn dieser Filter die Steuerung übergibt (0 zurückgibt), wird der Prozess fortgesetzt, bis ein Filter gefunden wird, der die Steuerung nicht übergibt.

1. If this filter returns -1, execution continues where the exception was raised, and no termination takes place.

1. Wenn der Filter 1 zurückgibt, werden folgende Ereignisse ausgelöst:

   - Das System entlädt den Stapel und löscht alle Stapelrahmen zwischen dem gerade ausgeführten Code (bei dem die Ausnahme ausgelöst wurde) und dem Stapelrahmen, der den Ausnahmehandler enthält, der nun die Steuerung übernimmt.

   - Beim Entladen des Stapels wird jeder Beendigungshandler im Stapel ausgeführt.

   - Der Ausnahmehandler selbst wird ausgeführt.

   - Die Steuerung wird nach dem Ende des Ausnahmehandlers an die Codezeile übergeben.

## <a name="see-also"></a>Siehe auch

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)