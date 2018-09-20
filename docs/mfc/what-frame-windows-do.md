---
title: Was tun, Frame Windows | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], about frame widows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b86b65d43fee16a0a2a8f03353c9700d6f0a5428
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423597"
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

