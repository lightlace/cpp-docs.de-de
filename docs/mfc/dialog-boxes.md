---
title: Dialogfelder
ms.date: 11/04/2016
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
ms.openlocfilehash: 18b4c4d1386716a0a3282b88d6fdf5a701abce08
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685796"
---
# <a name="dialog-boxes"></a>Dialogfelder

Anwendungen für Windows kommunizieren häufig über Dialogfelder mit dem Benutzer. [CDialog](../mfc/reference/cdialog-class.md) -Klasse stellt eine Schnittstelle zum Verwalten von Dialogfeldern C++ bereit. der visuelle Dialog-Editor vereinfacht das Entwerfen von Dialogfeldern und das Erstellen von Dialogfeldern, und die Code-Assistenten vereinfachen den Prozess der Initialisierung und Überprüfung der steuert in einem Dialogfeld und zum Sammeln der vom Benutzer eingegebenen Werte.

Dialog Felder enthalten Steuerelemente, einschließlich:

- Allgemeine Windows-Steuerelemente, wie z. b. Bearbeitungsfelder, Pushbuttons, Listenfelder, Kombinations Felder, Struktur Steuerelemente, Listen Steuerelemente und Status Indikatoren.

- ActiveX-Steuerelemente.

- Vom Besitzer gezeichnete Steuerelemente: Steuerelemente, die für das Zeichnen im Dialogfeld verantwortlich sind.

Die meisten Dialogfelder sind modal, die erfordern, dass der Benutzer das Dialogfeld schließt, bevor ein anderer Teil des Programms verwendet wird. Es ist jedoch möglich, Dialogfelder ohne Modus zu erstellen, mit denen Benutzer mit anderen Fenstern arbeiten können, während das Dialogfeld geöffnet ist. MFC unterstützt beide Arten von Dialogfeldern mit der Klasse `CDialog`. Die Steuerelemente werden mithilfe einer Dialogfeld Vorlagen-Ressource angeordnet und verwaltet, die mit dem [Dialog-Editor](../windows/dialog-editor.md)erstellt wurde.

[Eigenschaften Blätter](../mfc/property-sheets-mfc.md), auch als Registerkarten Dialogfelder bezeichnet, sind Dialogfelder, die "Seiten" unterschiedlicher Dialogfeld-Steuerelemente enthalten. Jede Seite enthält den Datei Ordner "Registerkarte" oben. Wenn Sie auf eine Registerkarte klicken, wird diese Seite am Anfang des Dialog Felds angezeigt.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Anpassen von mit VSTU Anzeigen eines Dialogfelds mit einem Menübefehl](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)

- [Dialog Feld Komponenten im Framework](../mfc/dialog-box-components-in-the-framework.md)

- [Modale und nicht modale Dialogfelder](../mfc/modal-and-modeless-dialog-boxes.md)

- [Eigenschaften Blätter und Eigenschaften Seiten](../mfc/property-sheets-and-property-pages-mfc.md) in einem Dialogfeld

- [Erstellen der Dialogfeld Ressource](../mfc/creating-the-dialog-resource.md)

- [Erstellen einer Dialogfeld Klasse mit Code-Assistenten](../mfc/creating-a-dialog-class-with-code-wizards.md)

- [Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)

- [Dialog Datenaustausch (DDX) und Validierung (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Typsicherer Zugriff auf Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [Zuordnung von Windows-Meldungen zu ihrer Klasse](../mfc/mapping-windows-messages-to-your-class.md)

- [Häufig überschreibbare Memberfunktionen](../mfc/commonly-overridden-member-functions.md)

- [Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)

- [Allgemeine Dialogfeld Klassen](../mfc/common-dialog-classes.md)

- [Dialog Felder in OLE](../mfc/dialog-boxes-in-ole.md)

- Erstellen Sie eine Anwendung, deren Benutzeroberfläche ein Dialogfeld ist: siehe [CMNCTRL1](../overview/visual-cpp-samples.md) -oder [CMNCTRL2](../overview/visual-cpp-samples.md) -Beispiel Programme. Der Anwendungs-Assistent bietet auch diese Option.

- [Beispiele](../mfc/dialog-sample-list.md)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)
