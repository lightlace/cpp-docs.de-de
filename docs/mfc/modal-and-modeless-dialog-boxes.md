---
title: Modale und nicht modale Dialogfelder | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e355c3bcef9edb68e49903dafbf4719fe0aa925
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417526"
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

