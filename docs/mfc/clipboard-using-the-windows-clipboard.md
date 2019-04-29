---
title: 'Zwischenablage: Verwenden der Windows-Zwischenablage'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
ms.openlocfilehash: 49111e4efd2a12264d61030fe038d80b974514c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326988"
---
# <a name="clipboard-using-the-windows-clipboard"></a>Zwischenablage: Verwenden der Windows-Zwischenablage

In diesem Thema wird beschrieben, wie Sie mit der standardmäßigen Windows-Zwischenablage-API in Ihrer MFC-Anwendung.

Die meisten Anwendungen für Windows unterstützt Ausschneiden oder Kopieren von Daten in die Windows-Zwischenablage und Einfügen von Daten aus der Zwischenablage. Die zwischenablagedatenformate variieren zwischen Anwendungen. Das Framework unterstützt nur eine begrenzte Anzahl von Standardformaten der Zwischenablage für eine begrenzte Anzahl von Klassen. Normalerweise implementieren Sie die Zwischenablage-bezogenen Befehlen – Ausschneiden, kopieren und einfügen, auf das Menü "Bearbeiten" für die Ansicht. Die Klassenbibliothek definiert die Befehls-IDs für diese Befehle: **ID_EDIT_CUT**, **ID_EDIT_COPY**, und **ID_EDIT_PASTE**. Die Message-Line-Anweisungen sind auch definiert.

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md) wird erläutert, wie Menübefehle in Ihrer Anwendung zu behandeln, indem Sie den Menübefehl eine Handlerfunktion zuordnen. Solange Handlerfunktionen für die Zwischenablage-Befehle nicht auf das Menü "Bearbeiten" Ihrer Anwendung definiert ist, bleiben sie deaktiviert. Zum Schreiben von Handlerfunktionen für die Befehle zum Ausschneiden und kopieren implementieren Sie Auswahl in Ihrer Anwendung. Fragen Sie ab, um eine Handlerfunktion für den Befehl "Einfügen" zu schreiben, die Zwischenablage, um festzustellen, ob sie Daten in einem Format enthält, die Ihre Anwendung annehmen kann. Beispielsweise können zum Aktivieren des Kopierbefehls Sie einen Handler etwa wie folgt schreiben:

[!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]

Das Ausschneiden, kopieren und Einfügen-Befehle sind nur in bestimmten Fällen sinnvoll. Nur, wenn etwas ausgewählt ist und der Befehl "Einfügen", nur, wenn etwas in der Zwischenablage ist, sollte die Ausschneiden und kopieren Befehle aktiviert werden. Sie können dieses Verhalten angeben, durch die Definition der Update-Handlerfunktionen, die aktivieren oder deaktivieren diese Befehle je nach Kontext. Weitere Informationen finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md).

Die Microsoft Foundation Class-Bibliothek bietet Unterstützung der Zwischenablage für die Textbearbeitung mit der `CEdit` und `CEditView` Klassen. Der OLE-Klassen vereinfachen zudem die implementierende Zwischenablageoperationen, die OLE-Elemente enthalten. Weitere Informationen zu den OLE-Klassen, finden Sie unter [Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md).

Implementieren andere Menübefehle, z. B. "Rückgängig" Bearbeiten (**ID_EDIT_UNDO**) und "Wiederherstellen" (**ID_EDIT_REDO**), bleibt auch für Sie. Wenn Ihre Anwendung diese Befehle nicht unterstützt, können Sie sie aus der Ressourcendatei, die mit den Visual C++-Ressourcen-Editoren einfach löschen.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)

- [Verwenden des OLE-zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

## <a name="see-also"></a>Siehe auch

[Zwischenablage](../mfc/clipboard.md)
