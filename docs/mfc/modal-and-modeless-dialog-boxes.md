---
title: Modale und nicht modale Dialogfelder
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: 886229a2b66968bf76129ecb1da838bd36e66215
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685183"
---
# <a name="modal-and-modeless-dialog-boxes"></a>Modale und nicht modale Dialogfelder

Sie können [CDialog](../mfc/reference/cdialog-class.md) -Klasse verwenden, um zwei Arten von Dialogfeldern zu verwalten:

- *Modale Dialogfelder*, die erfordern, dass der Benutzer antwortet, bevor das Programm fortgesetzt wird

- Nicht *modante Dialogfelder*, die auf dem Bildschirm bleiben und jederzeit zur Verwendung verfügbar sind, aber andere Benutzeraktivitäten zulassen

Die Ressourcen Bearbeitung und die Prozeduren zum Erstellen einer Dialogfeld Vorlage sind für modale und nicht modale Dialogfelder identisch.

Zum Erstellen eines Dialog Felds für das Programm sind die folgenden Schritte erforderlich:

1. Verwenden Sie den [Dialog-Editor](../windows/dialog-editor.md) , um das Dialogfeld zu entwerfen und seine Dialogfeld Vorlagen-Ressource zu erstellen.

1. Erstellen Sie eine Dialogfeld Klasse.

1. Verbinden Sie die Steuer [Elemente der Dialogfeld Ressource mit Nachrichten Handlern](../windows/adding-event-handlers-for-dialog-box-controls.md) in der Dialogfeld Klasse.

1. Fügen Sie Datenelemente hinzu, die den Steuerelementen des Dialog Felds zugeordnet sind, und, um die Überprüfungen des [Dialog](../mfc/dialog-data-exchange.md) Feld-und [Dialog Daten](../mfc/dialog-data-validation.md) für die Steuerelemente anzugeben

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)
