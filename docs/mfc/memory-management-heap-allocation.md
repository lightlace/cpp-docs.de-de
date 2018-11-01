---
title: 'Speicherverwaltung: Heapbelegung'
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
ms.openlocfilehash: 0c669fa611193b9a04e4854c84dec604e585991c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641154"
---
# <a name="memory-management-heap-allocation"></a>Speicherverwaltung: Heapbelegung

Der Heap ist für die arbeitsspeicheranforderungen für die Zuordnung des Programms reserviert. Es ist ein Bereich von Programmcode und den Stapel. Typische C-Programmen. verwenden Sie die Funktionen **Malloc** und **kostenlose** zum Reservieren und Freigeben von Speicher für den Heap. Die Debugversion von MFC bietet geänderte Versionen von den integrierten C++-Operatoren **neue** und **löschen** zum Reservieren und Freigeben von Objekten im Heap-Arbeitsspeicher.

Bei Verwendung von **neue** und **löschen** anstelle von **Malloc** und **kostenlose**, können Sie der Klassenbibliothek nutzen Speicher-Management-debugverbesserungen, die was bei der Erkennung von Speicherverlusten nützlich sein kann. Das Programm mit der Version von MFC, die Versionen standard, der beim Erstellen der **neue** und **löschen** Operatoren bieten eine effiziente Möglichkeit zum Reservieren und Freigeben von Speicher (die veröffentlichte Version von MFC stellt keine geänderte Versionen dieser Operatoren bereit).

Beachten Sie, dass die Gesamtgröße der Objekte, die auf dem Heap reserviert nur durch den verfügbaren Speichers des Systems beschränkt ist.

## <a name="see-also"></a>Siehe auch

[Speicherverwaltung](../mfc/memory-management.md)

