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
ms.openlocfilehash: 400107a7b61ae28ca1d3ec69ee3217d58f55d9e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665074"
---
# <a name="dialog-boxes"></a>Dialogfelder

Anwendungen für Windows an, die häufig mit dem Benutzer in Dialogfeldern kommuniziert. Klasse [CDialog](../mfc/reference/cdialog-class.md) stellt eine Schnittstelle bereit, verwalten die Dialogfelder, die Visual C++-Dialog-Editor erleichtert Dialogfelder zu entwerfen und erstellen Sie die Dialogfeld-Vorlagenressourcen und Code-Assistenten vereinfachen den Prozess für die Initialisierung und Überprüfen die Steuerelemente in einem Dialogfeld und der vom Benutzer eingegebenen Werte zu sammeln.

Dialogfelder enthält Steuerelemente, einschließlich:

- Windows-Standardsteuerelemente bearbeiten wie z. B. Textfelder, Druckknöpfe, Listenfelder, Kombinationsfelder, Struktur-Steuerelemente, Listensteuerelementen und Statusanzeigen.

- ActiveX-Steuerelemente.

- Ownerdrawn-Schaltflächen: Steuerelemente, die Sie für das Zeichnen im Dialogfeld verantwortlich sind.

Die meisten Dialogfelder sind modal, die erfordern, dass des Benutzers das Dialogfeld zu schließen, bevor Sie mit anderen Teilen des Programms. Aber es ist möglich, das nicht modale Dialogfelder zu erstellen, die Benutzer an andere Fenster zu arbeiten, während das Dialogfeld geöffnet ist. MFC unterstützt beide Arten von Dialogfeld mit der Klasse `CDialog`. Die Steuerelemente angeordnet werden und mit einer Dialogfeldvorlagen-Ressource, die mit erstellt verwaltet die [Dialog-Editor](../windows/dialog-editor.md).

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md), auch bekannt als Registerkarte angezeigten Dialogfelder und Dialogfelder, die "Seiten" von unterschiedlichen Dialogfeld-Steuerelemente enthalten sind. Jede Seite verfügt über einen Dateiordner "Register" oben. Klicken Sie auf einer Registerkarte öffnet dieser Seite im Vordergrund des Dialogfelds.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Beispiel: Anzeigen eines Dialogfelds mit einem Menübefehl](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)

- [Dialogfeld-Steuerelemente im framework](../mfc/dialog-box-components-in-the-framework.md)

- [Modale und nicht modale Dialogfelder](../mfc/modal-and-modeless-dialog-boxes.md)

- [Eigenschaftenblätter und Eigenschaftenseiten](../mfc/property-sheets-and-property-pages-mfc.md) in einem Dialogfeld

- [Erstellen der Dialogfeldressource](../mfc/creating-the-dialog-resource.md)

- [Erstellen einer Dialogfeldklasse mit Code-Assistenten](../mfc/creating-a-dialog-class-with-code-wizards.md)

- [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

- [Dialogdatenaustausch (DDX) und Überprüfung (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Typsicherer Zugriff auf Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [Zuordnen von Windows-Meldungen zu einer Klasse](../mfc/mapping-windows-messages-to-your-class.md)

- [Häufig überschreibbare Memberfunktionen](../mfc/commonly-overridden-member-functions.md)

- [Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)

- [Allgemeine Dialogfeldklassen](../mfc/common-dialog-classes.md)

- [Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md)

- Erstellen Sie eine Anwendung, deren Benutzeroberfläche ein Dialogfeld ist: finden Sie unter den [CMNCTRL1](../visual-cpp-samples.md) oder [CMNCTRL2](../visual-cpp-samples.md) Beispielprogramme. Der Anwendungs-Assistent bietet diese Option ebenfalls.

- [Beispiele](../mfc/dialog-sample-list.md)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)
