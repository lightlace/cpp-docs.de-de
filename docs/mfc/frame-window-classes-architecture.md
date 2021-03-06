---
title: Klassen für Rahmenfenster (Architektur)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: affa217f481cc6d9e125d526f1b97be9120e0990
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392842"
---
# <a name="frame-window-classes-architecture"></a>Klassen für Rahmenfenster (Architektur)

In der Dokument-/Ansichtarchitektur sind Rahmenfenster Windows, die ein Fenster enthalten. Außerdem unterstützen Sie steuern, dass Balken angefügt werden.

In Anwendungen für mehrere Dokumente Interface (MDI), wird im Hauptfenster von abgeleitet `CMDIFrameWnd`. Es enthält indirekt die Dokumente-Frames, die sind `CMDIChildWnd` Objekte. Die `CMDIChildWnd` Objekte wiederum enthalten, die Dokumente Ansichten.

In Anwendungen für einzelne Dokumente Interface (SDI), klicken Sie im Hauptfenster von abgeleitet `CFrameWnd`, enthält die Ansicht des aktuellen Dokuments.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Die Basisklasse für das Hauptrahmenfenster einer SDI-Anwendung. Auch die Basisklasse für alle anderen Klassen für Rahmenfenster.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
Die Basisklasse für das Hauptrahmenfenster für MDI-Anwendung.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Die Basisklasse für eine MDI-Anwendung Dokumentrahmenfenster.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Stellt das Rahmenfenster für eine Sicht, wenn Serverdokument direkt bearbeitet wird.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
