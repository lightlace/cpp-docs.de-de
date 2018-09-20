---
title: Erstellen die MFC-Anwendung ein Datei-Explorer-ähnliche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcexplorer.project
dev_langs:
- C++
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff6e3796de3f37275d136cc378e402d4c3272637
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442200"
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>Erstellen einer MFC-Anwendung im Stil des Datei-Explorers

Viele Windows-System-Anwendungen verwenden Sie die Benutzeroberfläche (UI) für Datei-Explorer. Wenn Sie die Datei-Explorer starten, sehen Sie beispielsweise eine Anwendung mit einer vertikalen Trennleiste für das Aufteilen des Clientbereichs. Der linken Seite des Clientbereichs enthält Navigations- und Suchfunktionen, und der rechten Seite des Clientbereichs zeigt Details im linken Bereich für die Auswahl relevant sind. Klickt ein Benutzer ein Element im linken Bereich, füllt die Anwendung im rechten Bereich aus. Sie können Befehle in einer MDI-Anwendung verwenden, auf die **Ansicht** Menü so ändern Sie die Anzahl der Details im rechten Bereich angezeigt. (In einer SDI oder Anwendung für mehrere Dokumente der höchsten Ebene, können Sie die Details über die Symbolleisten-Schaltflächen ändern.)

Der Inhalt der Bereiche, hängt von der Anwendung ab. In einem Browser für das Dateisystem wird im linken Bereich eine hierarchische Ansicht der Verzeichnisse, Computern oder Computergruppen, auf, während der rechte Bereich, Ordner, einzelne Dateien oder Computer und Informationen zu diesen zeigt. Der Inhalt müssen nicht unbedingt Dateien sein. Sie können e-Mail-Nachrichten, Berichte oder andere Elemente in einer Datenbank sein.

Der Assistent erstellt die folgenden Klassen für Sie:

- Die `CLeftView` -Klasse definiert, im linken Bereich des Clientbereichs. Es wird immer von abgeleitet [CTreeView](../../mfc/reference/ctreeview-class.md).

- Das C*ProjName*View-Klasse definiert den rechten Bereich des Clientbereichs. In der Standardeinstellung es abgeleitet wird [CListView](../../mfc/reference/clistview-class.md) ist jedoch möglich, dass eine andere Art von Ansicht abhängig von der Klasse, die Sie angeben, aus der **Basisklasse** Liste der [generierte Klassen](../../mfc/reference/generated-classes-mfc-application-wizard.md) auf der Seite der Der Assistent.

Die generierte Anwendung kann es sich um single Document Interface (SDI), einer mehrfachen Dokumentschnittstelle (MDI) oder eine Architektur, die mehrere Dokumente der höchsten Ebene verfügen. Jede Rahmenfenster die Anwendung erstellt wird vertikal geteilt mit [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md). Coding diesen Anwendungstyp ist vergleichbar mit dem Codieren einer normalen MFC-Anwendung, die eine Trennleiste verwendet, mit dem Unterschied, dass diese Art von Anwendung separates Steuerelement-Ansichten innerhalb jedes Bereichs Splitter verfügt.

Wenn Sie die Standardansicht für die Liste im rechten Bereich verwenden, erstellt der Assistent zusätzliche Menüoptionen (in nur für MDI-Anwendungen) und Schaltflächen der Symbolleiste, um der Ansicht-Stil auf große Symbole, kleine Symbole, Liste und Details-Modus zu wechseln.

### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>Erstellen einer ausführbaren Datei-Explorer-ähnliche MFC

1. Befolgen Sie die Anweisungen [Erstellen einer MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md).

1. Im MFC-Anwendungs-Assistenten [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite die **Datei-Explorer** Projekt Stil.

1. Legen Sie ggf. Weitere Optionen, die Sie wünschen, auf den anderen Seiten des Assistenten.

1. Klicken Sie auf **Fertig stellen** um die skelettanwendung zu erzeugen.

Weitere Informationen finden Sie unter:

- [Mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md)

- [Abgeleitete Ansichtsklassen](../../mfc/derived-view-classes-available-in-mfc.md)

- [Überlegungen zum Anwendungsentwurf](../../mfc/application-design-choices.md)

## <a name="see-also"></a>Siehe auch

[MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)<br/>
[Erstellen einer MFC-Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)<br/>
[Erstellen einer formularbasierten MFC-Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md)

