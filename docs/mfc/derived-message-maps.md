---
title: Abgeleitete Meldungszuordnungen
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
ms.openlocfilehash: 1413290bc04af37a6d3204150dff5244e1dcb5c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662526"
---
# <a name="derived-message-maps"></a>Abgeleitete Meldungszuordnungen

Während der Nachrichtenverarbeitung verarbeiten, überprüfen eine Nachricht von der Klasse ist die Zuordnung nicht das Ende des Textabschnitts meldungszuordnung. Was geschieht, wenn Klasse `CMyView` (abgeleitet von `CView`) wurde kein übereinstimmenden Eintrag für eine Nachricht

Beachten Sie, dass `CView`, die Basisklasse der `CMyView`, ergibt sich wiederum aus `CWnd`. Daher `CMyView` *ist* eine `CView` und *ist* eine `CWnd`. Jede dieser Klassen hat ihre eigene meldungszuordnung. Beachten Sie in der Abbildung "Eine Hierarchie von Inhaltsansichten" unten zeigt die hierarchische Beziehung der Klassen, aber beachten Sie, dass eine `CMyView` Objekt stellt ein einzelnes Objekt mit den Eigenschaften der alle drei Klassen.

![Ansichtshierarchie](../mfc/media/vc38621.gif "vc38621") eine Hierarchie von Inhaltsansichten

Wenn eine Meldung in Klasse nicht realisiert werden kann `CMyView`meldungszuordnung, die das Framework auch auf die meldungszuordnung, die von den direkten Basisklassen gesucht. Die `BEGIN_MESSAGE_MAP` Makro am Anfang der meldungszuordnung gibt zwei Klassennamen als Argumente an:

[!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/cpp/derived-message-maps_1.cpp)]

Das erste Argument benennt die Klasse, zu der die meldungszuordnung gehört. Das zweite Argument stellt eine Verbindung mit einer direkten Basisklasse – `CView` hier, sodass das Framework seine meldungszuordnung, zu suchen kann.

Der Meldungshandler, der in einer Basisklasse werden daher von der abgeleiteten Klasse geerbt. Dies ist ohne Handler Memberfunktionen virtuellen stellen normale virtuelle Memberfunktionen sehr ähnlich.

Wenn in einem von der Basisklasse meldungszuordnungen kein Handler gefunden wird, wird die standardmäßige Verarbeitung der Nachricht ausgeführt. Wenn die Nachricht einen Befehl handelt, wird es von das Framework an das Ziel des nächsten Befehls weitergeleitet. Wenn es sich um eine standard-Windows-Nachricht handelt, wird die Nachricht an die entsprechenden Standardfensterprozedur übergeben.

Um übereinstimmende meldungszuordnung – zu beschleunigen, speichert das Framework aktuelle Übereinstimmungen mit der Wahrscheinlichkeit, dass es die gleiche Nachricht erneut empfangen werden. Eine Folge davon ist, dass die Framework-Prozesse Nachrichten nicht sehr effizient behandelt. Meldungszuordnungen sind auch Speicherplatz-effizienter als Implementierungen, die virtuelle Funktionen verwenden.

## <a name="see-also"></a>Siehe auch

[So durchsucht das Framework Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md)

