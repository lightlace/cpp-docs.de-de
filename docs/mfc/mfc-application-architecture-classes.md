---
title: Klassen der MFC-Anwendungsarchitektur
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
ms.openlocfilehash: 47feeb056d02b81bb88ccf3c5fd49bc983583ee7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239304"
---
# <a name="mfc-application-architecture-classes"></a>Klassen der MFC-Anwendungsarchitektur

Klassen, die in dieser Kategorie unterstützen Sie bei der Architektur einer frameworkanwendung. Sie geben die Funktionen, die in den meisten Anwendungen. Füllen Sie das Framework-Anwendung-spezifische Funktionen hinzufügen. In der Regel tun Sie durch Ableiten von neuen Klassen aus dem Architektur-Klassen, und klicken Sie dann auf neue Elemente hinzufügen oder Überschreiben von vorhandenen Memberfunktionen.

[Anwendungs-Assistenten](../mfc/reference/mfc-application-wizard.md) generiert verschiedene Arten von Anwendungen, die das Framework auf unterschiedliche Weise verwenden. (Einzelnes Dokument-Schnittstelle)-SDI und MDI (mehrerer dokumentoberflächen)-Anwendungen nutzen einen Teil des Frameworks, die Dokument-/Ansichtarchitektur aufgerufen. Andere Arten von Anwendungen, z. B. auf Dialogfeldern basierende Anwendungen, formularbasierte Anwendungen und DLLs, verwenden Sie nur einige der Features der Dokument-/Ansicht-Architektur.

Dokument-/ansichtsanwendungen enthalten eine oder mehrere Dokumente, Ansichten und Rahmenfenster. Eine Dokumentvorlagenobjekt ordnet die Klassen für jeden Satz von Dokument/Ansicht/Frame.

Obwohl Sie nicht in der MFC-Anwendung Dokument-/Ansichtarchitektur verwendet, gibt es eine Reihe von Vorteilen zu tun. Die MFC-OLE-Container und Server Unterstützung basiert auf Dokument-/Ansichtarchitektur wie ist die Unterstützung für das Drucken und Druckvorschau.

Alle MFC-Anwendungen verfügen über mindestens zwei Objekte: ein Anwendungsobjekt abgeleitet [CWinApp](../mfc/reference/cwinapp-class.md), und eine Art von main Window-Objekt (häufig indirekt) abgeleitet [CWnd](../mfc/reference/cwnd-class.md). (In den meisten Fällen wird im Hauptfenster von abgeleitet [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), oder [CDialog](../mfc/reference/cdialog-class.md), die davon abgeleitet sind `CWnd`.)

Anwendungen, die Dokument-/Ansichtarchitektur verwenden werden zusätzliche Objekte enthalten. Die principal-Objekte sind:

- Ein Anwendungsobjekt abgeleitet wird, aus der Klasse [CWinApp](../mfc/reference/cwinapp-class.md), wie bereits erwähnt.

- Ein oder mehrere Objekte der Dokument-Klasse, die von der Klasse abgeleitet [CDocument](../mfc/reference/cdocument-class.md). Dokument-Klassenobjekten sind verantwortlich für die interne Darstellung der Daten in der Ansicht bearbeitet. Sie können eine Datendatei zugeordnet werden.

- Eine oder mehrere Objekte, die von der Klasse abgeleitet [CView](../mfc/reference/cview-class.md). Jede Sicht ist ein Fenster, das an ein Dokument angefügt und ein Rahmenfenster zugeordnet ist. Ansichten anzeigen und bearbeiten die Daten in ein Dokument-Klassenobjekt.

Dokument-/ansichtsanwendungen enthalten auch die Frame-Fensters (abgeleitet [CFrameWnd](../mfc/reference/cframewnd-class.md)) und Dokumentieren von Vorlagen (abgeleitet von [CDocTemplate](../mfc/reference/cdoctemplate-class.md)).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
