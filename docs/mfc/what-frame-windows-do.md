---
title: Funktionsweise von Rahmenfenstern
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], about frame windows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
ms.openlocfilehash: 594700ef1cbe0030bbe452adaa40b29b4a72f4d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405676"
---
# <a name="what-frame-windows-do"></a>Funktionsweise von Rahmenfenstern

Neben der einfachen Einrahmen einer Ansicht, sind die Rahmenfenster für zahlreiche Aufgaben, die beim Koordinieren des Frames mit der Ansicht und die Anwendung verantwortlich. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) erben [CFrameWnd](../mfc/reference/cframewnd-class.md), sodass sie `CFrameWnd` Funktionen sowie die neuen Funktionen, die sie hinzufügen. Beispiele für untergeordnete Fenster sind Ansichten und Steuerelemente wie Schaltflächen und Listenfelder und Steuerleisten, einschließlich der Symbolleisten, Statusleisten und Dialogleisten.

Das Rahmenfenster ist verantwortlich für das Layout der zugehöriges untergeordnetes Fenster verwalten. In MFC-Framework positioniert ein Rahmenfenster alle Schiebeleisten-Steuerelemente, Ansichten und andere untergeordnete Fenster innerhalb seines Clientbereichs.

Das Rahmenfenster leitet auch die Befehle aus, um die Ansichten und Benachrichtigungen von steuerelementfenstern reagieren kann.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Steuerleisten (wie sie in das Rahmenfenster passen)](../mfc/control-bars.md)

- [Verwalten von Menüs, Steuerleisten und Zugriffstasten (wie sie in das Rahmenfenster passen)](../mfc/managing-menus-control-bars-and-accelerators.md)

- [Befehlsrouting (über das Rahmenfenster der anzeigen und andere Befehlsziele)](../mfc/command-routing.md)

- [Document/View Architecture](../mfc/document-view-architecture.md)

- [Steuerleisten](../mfc/control-bars.md)

- [Steuerelemente](../mfc/controls-mfc.md)

## <a name="see-also"></a>Siehe auch

[Rahmenfenster](../mfc/frame-windows.md)
