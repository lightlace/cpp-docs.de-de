---
title: Vom Anwendungs-Assistenten erstellte Rahmenfensterklassen
ms.date: 11/04/2016
f1_keywords:
- CMainFrame
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
ms.openlocfilehash: 46da8fc0cb98406bdf97285d7c6f824afd61c4bb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808351"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Vom Anwendungs-Assistenten erstellte Rahmenfensterklassen

Wenn Ihnen die Erstellung einer neuen MFC Projekt aus der **neues Projekt** Dialogfeld zusätzlich zur Anwendung, Dokument- und Ansichtsklassen, die Anwendungs-Assistent erstellt eine Klasse abgeleiteten Rahmenfenster für das Hauptrahmenfenster Ihrer Anwendung. Die Klasse wird aufgerufen, `CMainFrame` standardmäßig, und die Dateien, die es enthalten bezeichnet. H und MAINFRM. CPP.

Wenn Ihre Anwendung SDI, ist Ihre `CMainFrame` abgeleitete Klasse wird von Klasse [CFrameWnd](../mfc/reference/cframewnd-class.md).

Wenn Ihre Anwendung MDI, `CMainFrame` ergibt sich aus der Klasse [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md). In diesem Fall `CMainFrame` implementiert den Hauptframe, die die leisten Menüs, Symbolleisten und Status enthält. Der Anwendungs-Assistent ist eine neue Klasse der Dokument-Rahmenfenster für Sie nicht abgeleitet werden. Stattdessen wird die standardmäßige Implementierung in [CMDIChildWnd-Klasse](../mfc/reference/cmdichildwnd-class.md). MFC-Framework erstellt ein untergeordnetes Fenster, sodass jede Ansicht enthält (vom Typ stehen `CScrollView`, `CEditView`, `CTreeView`, `CListView`und so weiter), die die Anwendung erforderlich sind. Wenn Sie Ihre Dokumentrahmenfenster anpassen müssen, können Sie eine neue Klasse der Dokument-Rahmenfenster erstellen (siehe [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)).

Wenn Sie auswählen, um eine Symbolleiste zu unterstützen, die Klasse verfügt auch über Membervariablen des Typs [CToolBar](../mfc/reference/ctoolbar-class.md) und [CStatusBar](../mfc/reference/cstatusbar-class.md) und `OnCreate` Meldungshandler-Funktion zum Initialisieren der beiden [ Steuerleisten](../mfc/control-bars.md).

Diese Klassen für Rahmenfenster können nach dem Erstellen, aber um ihre Funktionalität zu verbessern, müssen Sie die Membervariablen und Member-Funktionen hinzufügen. Möglicherweise möchten Sie auch Ihre Klassen für andere Windows-Meldungen zu verarbeiten haben. Weitere Informationen finden Sie unter [Ändern der Stile eines mit MFC erstellten Fenster](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Siehe auch

[Rahmenfensterklassen](../mfc/frame-window-classes.md)<br/>
[MFC-Programm oder Steuern von Quell- und Headerdateien](../build/reference/mfc-program-or-control-source-and-header-files.md)

