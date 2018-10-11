---
title: 'Speicherverwaltung: Frame-Zuordnung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory leaks [MFC], frame allocation
- memory [MFC], detecting leaks
- memory [MFC], reclaiming
- memory allocation [MFC], frames
- frame variables [MFC], automatic deletion of
- scope [MFC], frame variables
- heap allocation [MFC], vs. frame allocation
- variables [MFC], frame variables
- memory leaks [MFC], detecting
- memory, releasing [MFC]
- stack frames [MFC]
- memory leaks [MFC], allocating objects on the frame
- detecting memory leaks [MFC]
- frame allocation [MFC]
- frame variables [MFC]
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1138a675d64561a2e8399accd93c4ebb5eff382d
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083860"
---
# <a name="memory-management-frame-allocation"></a>Speicherverwaltung: Rahmenzuordnung

Zuweisung auf den Frame hat seinen Namen aus der "Stapelrahmen", der festgelegt wird einrichten, wenn eine Funktion aufgerufen wird. Der Stapelrahmen ist einem Bereich des Arbeitsspeichers, der vorübergehend enthält die Argumente der Funktion als auch für alle Variablen, die definiert sind, die für die Funktion lokal. Framevariablen werden häufig "Automatische" Variablen bezeichnet, da der Compiler automatisch den Speicherplatz für sie reserviert.

Es gibt zwei wichtige Merkmale der Frame-Zuordnungen. Zuerst, wenn Sie eine lokale Variable definieren, wird genügend Speicherplatz auf dem Stapelrahmen, um die gesamte Variable speichern zugeordnet, selbst wenn es sich um ein großes Array oder eine Datenstruktur ist. Andererseits wird Framevariablen werden automatisch gelöscht, wenn sie den Gültigkeitsbereich verlassen:

[!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/cpp/memory-management-frame-allocation_1.cpp)]

Für lokale Variablen erfolgt dieser Übergang Bereich auf, wenn die Funktion beendet wird, aber den Rahmen einer-Framevariablen kleiner als eine Funktion werden können, wenn geschachtelte Klammern verwendet werden. Diese automatische Löschen von Framevariablen ist sehr wichtig. Im Fall von einfacher, primitiver Typen (z. B. **Int** oder **Byte**), Arrays oder Datenstrukturen, das automatische Löschen einfach gibt den Speicher frei, die von der Variablen verwendet. Da die Variable den Gültigkeitsbereich verlassen hat, kann es dennoch zugegriffen werden. Im Fall von C++-Objekten ist der Prozess des automatischen Löschvorgangs jedoch etwas komplizierter.

Wenn ein Objekt als Framevariable definiert ist, wird seinem Konstruktor automatisch an der Stelle aufgerufen, in dem die Definition gefunden wird. Wenn das Objekt den Gültigkeitsbereich verlässt, wird dessen Destruktor automatisch aufgerufen, bevor der Speicher für das Objekt freigegeben wird. Diese automatische Konstruktion und Zerstörung können sehr nützlich sein, aber Sie müssen über die automatische Aufrufe, insbesondere der Destruktor sein.

Der Hauptvorteil der Zuweisung von Objekten im Frame ist, dass sie automatisch gelöscht werden. Wenn Sie Ihre Objekte im Bereich zuordnen, müssen Sie kümmern vergessen haben Objekte einen Speicherverlust verursacht. (Ausführliche Informationen zu Speicherverlusten, finden Sie im Artikel [feststellen von Speicherverlusten in MFC](/previous-versions/visualstudio/visual-studio-2010/c99kz476).) Ein Nachteil von rahmenzuordnung ist Framevariablen außerhalb ihres Bereichs können nicht verwendet werden. Ein weiterer Faktor bei der Auswahl rahmenzuordnung im Vergleich zu Heapzuordnung ist, dass große Strukturen und-Objekten es oft besser ist, den Heap anstatt des Stapels für den Speicher verwenden, da Stapelspeicher häufig beschränkt ist.

## <a name="see-also"></a>Siehe auch

[Speicherverwaltung](../mfc/memory-management.md)

