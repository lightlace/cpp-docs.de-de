---
title: Erstellen das Datum und Uhrzeit des Steuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 864d6cfef599da61238baa92f7ab01a8ad82229d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393294"
---
# <a name="creating-the-date-and-time-picker-control"></a>Erstellen des Steuerelements für Datum und Uhrzeit

Wie die Datums- / Zeitauswahl-Steuerelement erstellt wird, hängt davon ab, ob Sie mithilfe des Steuerelements in einem Dialogfeld oder erstellen es in einer nicht-Dialogfenster.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>Verwenden von CDateTimeCtrl direkt in einem Dialogfeld

1. Der Dialog-Editor fügen Sie ein Datum und die / Zeitauswahl-Steuerelement auf der Dialogfeldvorlagen-Ressource ein. Geben Sie die Steuerelement-ID.

1. Geben Sie alle erforderlichen Formate mithilfe des Dialogfelds "Eigenschaften" von den Datums- / Zeitauswahl-Steuerelement.

1. Verwenden der [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md) zum Hinzufügen einer Membervariablen des Typs [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) mit der Eigenschaft des Steuerelements. Sie können diesen Member Aufrufen `CDateTimeCtrl` Memberfunktionen.

1. Verwenden Sie das Fenster "Eigenschaften", um Handlerfunktionen in die Dialogfeldklasse für alle Datums-/ Zeitauswahl-Steuerelement zuzuordnen [Benachrichtigung](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) Nachrichten behandelt werden müssen (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

1. In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie ggf. Weitere Formate für die `CDateTimeCtrl` Objekt.

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>Zum Verwenden von CDateTimeCtrl in einem nicht-Dialogfenster

1. Deklarieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.

1. Aufrufen des Steuerelements [erstellen](../mfc/reference/ctabctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so frühzeitig wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler-Funktion (Wenn Sie sind Erstellen von Unterklassen für das Steuerelement). Legen Sie die Formate für das Steuerelement.

## <a name="see-also"></a>Siehe auch

[Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

