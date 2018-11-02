---
title: Klassen zur Befehlsweiterleitung
ms.date: 11/04/2016
f1_keywords:
- vc.classes.command
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
ms.openlocfilehash: 637f2056b76b7d55933b43a8e0822ec00212301a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574758"
---
# <a name="command-routing-classes"></a>Klassen zur Befehlsweiterleitung

Während der Benutzer mit der Anwendung interagiert, indem Sie die Menüs oder Schaltflächen Steuerleiste, mit der Maus auswählen, sendet die Anwendung Nachrichten aus dem betroffenen Benutzeroberflächen-Objekt, um ein Befehlsziel Objekt. Abgeleitet von befehlszielklassen `CCmdTarget` enthalten [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), und die Klassen, die von ihnen abgeleitet. Das Framework unterstützt das automatische routing, sodass Befehle vom derzeit aktiven in der Anwendung am besten geeigneten Objekt behandelt werden können.

Ein Objekt der Klasse `CCmdUI` UI-Befehl für das Update von Befehlsziele übergeben wird ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) Handler, die Ihnen ermöglichen, den Zustand der Benutzeroberfläche für einen bestimmten Befehl zu aktualisieren (z. B. zu überprüfen oder entfernen die Überprüfung von Menüelementen). Sie rufen Memberfunktionen der `CCmdUI` Objekt, das den Zustand des UI-Objekts zu aktualisieren. Dieser Prozess ist identisch, ob das UI-Objekt, das einen bestimmten Befehl zugeordnet, ein Menüelement oder eine Schaltfläche oder beides ist.

[CCmdTarget](../mfc/reference/ccmdtarget-class.md)<br/>
Dient als Basisklasse für alle Objektklassen, die empfangen und auf Nachrichten antworten können.

[CCmdUI](../mfc/reference/ccmdui-class.md)<br/>
Stellt eine programmgesteuerte Schnittstelle zum Aktualisieren von Benutzeroberflächenobjekten wie z. B. Steuerleiste-Schaltflächen oder Menüelemente an. Das Zielobjekt für den Befehl aktiviert, deaktiviert, überprüft und/oder löscht das Benutzeroberflächen-Objekt mit diesem Objekt.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

