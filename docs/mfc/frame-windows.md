---
title: Rahmen für Windows | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame widows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77035b50070478f5117635738f13c7bfd43edec2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431020"
---
# <a name="frame-windows"></a>Rahmenfenster

Wenn eine Anwendung unter Windows ausgeführt wird, interagiert der Benutzer, mit Dokumenten, die im Frame-Fensters angezeigt. Einem Dokumentrahmenfenster hat zwei Hauptkomponenten: den Frame und den Inhalt, der ihn umgibt. Einem Dokumentrahmenfenster möglich einen [Einzeldokumentoberfläche](../mfc/sdi-and-mdi.md) Rahmenfenster (SDI) oder ein [mehrerer dokumentoberflächen](../mfc/sdi-and-mdi.md) (MDI) untergeordneten Fensters. Windows verwaltet die meisten der Interaktion des Benutzers mit dem Rahmenfenster: verschieben und Ändern der Größe des Fensters, schließen, und minimieren und Maximieren es. Sie verwalten den Inhalt innerhalb des Rahmens.

## <a name="frame-windows-and-views"></a>Frame-Windows und Ansichten

Das MFC-Framework verwendet Rahmenfenster für Ansichten. Die zwei Komponenten – Rahmen und Inhalt – dargestellt und von zwei verschiedenen Klassen in MFC verwaltet werden. Eine Rahmenfenster-Klasse verwaltet den Rahmen und eine View-Klasse verwaltet den Inhalt. Das Fenster ist ein untergeordnetes Element des Rahmenfensters. Zeichnen und andere Benutzerinteraktion mit dem Dokument erfolgen in der Ansicht Clientbereich, nicht das Rahmenfenster des Clientbereichs. Das Rahmenfenster bietet einen sichtbaren Rahmen um eine Ansicht, die mit einer Titelleiste und standard-Window-Steuerelemente, z. B. ein Steuerelementmenü, Schaltflächen zum Minimieren und Maximieren Sie das Fenster und Steuerelemente für das Ändern der Größe des Fensters. Die "Inhalt" bestehen des Clientbereichs des Fensters, das vollständig von einem untergeordneten Fenster belegt wird, die Ansicht. Die folgende Abbildung zeigt die Beziehung zwischen einem Rahmenfenster und einer Ansicht.

![Frame-Fenster "Ansicht"](../mfc/media/vc37fx1.gif "vc37fx1") Rahmenfenster und-Ansicht

## <a name="frame-windows-and-splitter-windows"></a>Frame-Windows und Windows der Splitter

Eine andere allgemeine Anordnung ist das Rahmenfenster mehrere Ansichten, die in der Regel mithilfe von Rahmen um ein [Teilungsfenster](../mfc/multiple-document-types-views-and-frame-windows.md). In einem Splitterfenster ist das Rahmenfenster des Clientbereichs durch eines unterteilten Fensters belegt, die wiederum mehrere untergeordnete Fenster, Bereiche, die Ansichten sind aufgerufen.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

**Rahmenfenster allgemeine Themen**

- [Fensterobjekte](../mfc/window-objects.md)

- [Klassen für Rahmenfenster](../mfc/frame-window-classes.md)

- [Die vom Anwendungs-Assistenten erstellten Rahmenfensterklassen](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [Frame-Window-Stile](../mfc/frame-window-styles-cpp.md)

- [Welche von Rahmenfenstern](../mfc/what-frame-windows-do.md)

**Themen zur Verwendung von Frame Windows**

- [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

- [Erstellen eines Dokuments Rahmenfenster](../mfc/creating-document-frame-windows.md)

- [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)

- [Verwalten von untergeordneten MDI-Fenster](../mfc/managing-mdi-child-windows.md)

- [Verwalten der aktuellen Ansicht](../mfc/managing-the-current-view.md) in einem Rahmenfenster, das mehrere Ansichten enthält.

- [Verwalten von Menüs, Steuerleisten und Zugriffstasten (andere Objekte, die das Rahmenfenster Speicherplatz freigeben)](../mfc/managing-menus-control-bars-and-accelerators.md)

**Themen zur speziellen Funktionalitäten von Rahmenfenstern**

- [Ziehen und Ablegen von Dateien](../mfc/dragging-and-dropping-files-in-a-frame-window.md) im Datei-Explorer oder Datei-Manager in einem Rahmenfenster

- [Reagieren auf dynamischen Datenaustausch (DDE)](../mfc/responding-to-dynamic-data-exchange-dde.md)

- [Halbmodaler Zustand: Windows-kontextbezogene Hilfe (orchestrieren anderer Fensteraktionen)](../mfc/orchestrating-other-window-actions.md)

- [Halbmodaler Zustand: Drucken und die Seitenansicht (orchestrieren anderer Fensteraktionen)](../mfc/orchestrating-other-window-actions.md)

**Themen zu anderen Arten von Windows**

- [Verwenden von Ansichten](../mfc/using-views.md)

- [Dialogfelder](../mfc/dialog-boxes.md)

- [Steuerelemente](../mfc/controls-mfc.md)

## <a name="see-also"></a>Siehe auch

[Windows](../mfc/windows.md)

