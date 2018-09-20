---
title: Verwenden von Struktursteuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc3efbf48a9005bf117c2dd7ab5f1bd01ed556d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403681"
---
# <a name="using-tree-controls"></a>Verwenden von Struktursteuerelementen

Typische Verwendung des Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) basiert auf dem folgenden Muster:

- Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben ist, oder bei Verwendung von `CTreeView`, Erstellung erfolgt automatisch, wenn das Dialogfeld oder eine Sicht erstellt wird. Wenn Sie die Strukturansicht-Steuerelement als untergeordnetes Fenster eines anderen Fensters erstellen möchten, verwenden Sie die [erstellen](../mfc/reference/ctreectrl-class.md#create) Member-Funktion.

- Wenn Sie Ihre Strukturansicht-Steuerelement, Bilder verwenden möchten, legen Sie eine Bildliste durch Aufrufen von [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist). Sie können auch den Einzug ändern, durch den Aufruf [SetIndent](../mfc/reference/ctreectrl-class.md#setindent). Ein guter Zeitpunkt, zu diesem Zweck wird [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (für Steuerelemente in Dialogfeldern) oder [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (für Ansichten).

- Einfügen von Daten in das Steuerelement durch Aufrufen der `CTreeCtrl`des [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) Funktion einmal für jedes Datenelement. `InsertItem` Gibt ein Handle für das Element, die, das Sie verwenden können, um später darauf, z. B. bei verweisen, Hinzufügen untergeordneter Elemente. Ein guter Zeitpunkt, um die Daten zu initialisieren ist in `OnInitDialog` (für Steuerelemente in Dialogfeldern) oder `OnInitialUpdate` (für Ansichten).

- Während der Benutzer mit dem Steuerelement interagiert, sendet er die verschiedenen Benachrichtigungen. Sie können angeben, dass eine Funktion, um die einzelnen Nachrichten verarbeiten, die Sie durch das Hinzufügen eines ON_NOTIFY_REFLECT-Makros in die nachrichtenzuordnung des Steuerelementfensters oder durch Hinzufügen einer ON_NOTIFY-Makro zu Ihrer übergeordneten Fensters meldungszuordnung verarbeiten möchten. Finden Sie unter [Benachrichtigungsmeldungen von Struktursteuerelementen](../mfc/tree-control-notification-messages.md) weiter unten in diesem Thema eine Liste der möglichen Benachrichtigungen.

- Rufen Sie die verschiedenen Satz Memberfunktionen, um Werte für das Steuerelement festzulegen. Änderungen, die Sie vornehmen können, umfassen den Einzug festlegen und ändern den Text, Image oder einem Element zugeordneten Daten.

- Verwenden Sie die verschiedenen Get-Funktionen, um den Inhalt des Steuerelements zu untersuchen. Sie können auch den Inhalt des Strukturansicht-Steuerelements mit Funktionen durchlaufen, mit die Sie Handles für übergeordnete, untergeordnete oder gleichgeordnete Elemente eines angegebenen Elements abrufen können. Sie können auch die untergeordneten Elemente eines bestimmten Knotens sortieren.

- Wenn Sie mit dem Steuerelement fertig sind, stellen Sie sicher, dass es ordnungsgemäß zerstört wird. Das Struktursteuerelement ist in einem Dialogfeld oder wenn es sich um eine Sicht ist es und `CTreeCtrl` Objekt wird automatisch zerstört. Wenn nicht der Fall, Sie sicherstellen, dass sowohl das Steuerelement müssen und die `CTreeCtrl` Objekt ordnungsgemäß zerstört werden.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

