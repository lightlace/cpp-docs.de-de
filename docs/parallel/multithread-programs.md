---
title: Multithreadprogramme
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
ms.openlocfilehash: fd10893ecd33d39b531b9451dec708ea31c121d4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267315"
---
# <a name="multithread-programs"></a>Multithreadprogramme

Ein Thread ist im Grunde einen Pfad für die Ausführung über ein Programm. Es ist auch die kleinste Einheit der Ausführung, das Win32 plant. Ein Thread besteht aus einem Stapel, den Zustand der CPU-Register, und einen Eintrag in der Ausführungsliste des Zeitplanungsmoduls System. Jeder Thread gibt alle des Prozesses Ressourcen frei.

Ein Prozess besteht aus einem oder mehreren Threads und den Code, Daten und andere Ressourcen eines Programms im Arbeitsspeicher. Typische Programmressourcen sind geöffneten Dateien, Semaphoren und dynamisch zugeordneten Speicher. Ein Programm ausgeführt wird, wenn der Systemscheduler einen Thread die ausführungssteuerung bietet. Der Scheduler wird bestimmt, welche Threads ausgeführt werden soll und wann sie ausgeführt werden soll. Threads mit niedrigerer Priorität möglicherweise warten, während Threads mit höherer Priorität ihre Tasks auszuführen. Auf Mehrprozessorcomputern kann der Planer einzelne Threads auf verschiedenen Prozessoren, um die CPU-Last für verschieben.

Jeder Thread in einem Prozess arbeitet unabhängig. Es sei denn, Sie füreinander sichtbar machen, werden die Threads einzeln ausgeführt und sind keine Kenntnis von anderen Threads in einem Prozess. Threads, die gemeinsame Nutzung allgemeiner Ressourcen müssen jedoch mithilfe von Semaphoren oder eine andere Methode für die prozessübergreifende Kommunikation auf ihre Arbeit koordinieren. Weitere Informationen zum Synchronisieren von Threads finden Sie unter [Schreiben von Win32-Multithreadprogrammen](writing-a-multithreaded-win32-program.md).

## <a name="see-also"></a>Siehe auch

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)
