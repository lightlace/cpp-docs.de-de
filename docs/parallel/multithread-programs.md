---
title: Multithreadprogramme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88c39590f27597d29a27ab60bbc95c3c46dc862c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416863"
---
# <a name="multithread-programs"></a>Multithreadprogramme

Ein Thread ist im Grunde einen Pfad für die Ausführung über ein Programm. Es ist auch die kleinste Einheit der Ausführung, das Win32 plant. Ein Thread besteht aus einem Stapel, den Zustand der CPU-Register, und einen Eintrag in der Ausführungsliste des Zeitplanungsmoduls System. Jeder Thread gibt alle des Prozesses Ressourcen frei.

Ein Prozess besteht aus einem oder mehreren Threads und den Code, Daten und andere Ressourcen eines Programms im Arbeitsspeicher. Typische Programmressourcen sind geöffneten Dateien, Semaphoren und dynamisch zugeordneten Speicher. Ein Programm ausgeführt wird, wenn der Systemscheduler einen Thread die ausführungssteuerung bietet. Der Scheduler wird bestimmt, welche Threads ausgeführt werden soll und wann sie ausgeführt werden soll. Threads mit niedrigerer Priorität möglicherweise warten, während Threads mit höherer Priorität ihre Tasks auszuführen. Auf Mehrprozessorcomputern kann der Planer einzelne Threads auf verschiedenen Prozessoren, um die CPU-Last für verschieben.

Jeder Thread in einem Prozess arbeitet unabhängig. Es sei denn, Sie füreinander sichtbar machen, werden die Threads einzeln ausgeführt und sind keine Kenntnis von anderen Threads in einem Prozess. Threads, die gemeinsame Nutzung allgemeiner Ressourcen müssen jedoch mithilfe von Semaphoren oder eine andere Methode für die prozessübergreifende Kommunikation auf ihre Arbeit koordinieren. Weitere Informationen zum Synchronisieren von Threads finden Sie unter [Schreiben von Win32-Multithreadprogrammen](writing-a-multithreaded-win32-program.md).

## <a name="see-also"></a>Siehe auch

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)