---
title: Klassen für Rahmenfenster (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
ms.openlocfilehash: 3e56bd0f449992118db75a44c39b6e0e15cb0d86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392792"
---
# <a name="frame-window-classes-windows"></a>Klassen für Rahmenfenster (Windows)

Frame-Fenster sind Fenster, die eine Anwendung oder einen Teil einer Anwendung für Stapelrahmen. Rahmenfenster enthalten in der Regel andere Fenster, z. B. Sichten, Symbolleisten und Statusleisten. Im Fall von `CMDIFrameWnd`, sie enthalten möglicherweise `CMDIChildWnd` indirekt Objekte.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Die Basisklasse für das Hauptrahmenfenster einer SDI-Anwendung. Auch die Basisklasse für alle anderen Klassen für Rahmenfenster.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
Die Basisklasse für das Hauptrahmenfenster für MDI-Anwendung.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Die Basisklasse für eine MDI-Anwendung Dokumentrahmenfenster.

[CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)<br/>
Ein halber Höhe Rahmenfenster, der in der Regel um unverankerte Symbolleisten sichtbar angezeigt.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Stellt das Rahmenfenster für eine Sicht, wenn Serverdokument direkt bearbeitet wird.

## <a name="related-class"></a>Verwandte Klasse

Klasse `CMenu` stellt eine Schnittstelle, über die Menüs von Ihrer Anwendung den Zugriff auf. Dies ist nützlich für das Bearbeiten von Menüs dynamisch zur Laufzeit; z. B. beim Hinzufügen oder Löschen von Menüelementen je nach Kontext. Obwohl die Menüs mit Frame-Fensters am häufigsten verwendet werden, können sie auch mit Dialogfeldern und anderen nicht untergeordneten Fenstern verwendet werden.

[CMenu](../mfc/reference/cmenu-class.md)<br/>
Kapselt eine `HMENU` Handle für die Menüleiste und Popupmenüs der Anwendung.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
