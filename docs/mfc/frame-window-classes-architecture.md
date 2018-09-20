---
title: Frame-Klassen (Architektur) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 117554b2c34853aa166c12d80b4821d3721e5992
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394126"
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

