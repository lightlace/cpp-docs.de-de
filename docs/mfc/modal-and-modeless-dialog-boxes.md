---
title: Modale und nicht modale Dialogfelder
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: c3a5263736324d7fe25066e8879d13b3a41768de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238411"
---
# <a name="modal-and-modeless-dialog-boxes"></a>Modale und nicht modale Dialogfelder

Sie können die Klasse [CDialog](../mfc/reference/cdialog-class.md) zum Verwalten von zwei Arten von Dialogfeldern:

- *Modale Dialogfelder*, die erfordern, dass des Benutzers reagieren kann, bevor Sie fortfahren das Programm

- *Nicht modale Dialogfelder*, die auf dem Bildschirm und sind für die Verwendung jederzeit verfügbar bleiben jedoch eine andere Aktivitäten des Benutzers zulassen

Die Ressource bearbeiten und-Verfahren zum Erstellen einer Dialogfeldvorlage entsprechen für modale und nicht modale Dialogfelder.

Erstellen eines Dialogfelds für das Programm erfordert die folgenden Schritte aus:

1. Verwenden der [Dialog-Editor](../windows/dialog-editor.md) entwerfen das Dialogfeld, und der Dialogfeldvorlagen-Ressource zu erstellen.

1. Erstellen einer Dialogfeldklasse.

1. Verbinden der [Dialog-Ressource Steuerelemente Meldungshandler](../windows/adding-event-handlers-for-dialog-box-controls.md) in die Dialogfeldklasse.

1. Hinzufügen von Datenelementen zugeordnet sind, an das Dialogfeld-Steuerelemente und [Dialogdatenaustausch](../mfc/dialog-data-exchange.md) und [Dialogfeld Daten Überprüfungen](../mfc/dialog-data-validation.md) für die Steuerelemente.

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
