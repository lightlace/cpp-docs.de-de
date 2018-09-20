---
title: Erstellen des Monatskalender-Steuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0fadc3b56d0aa64068071ee7230ed125c6af925
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410870"
---
# <a name="creating-the-month-calendar-control"></a>Erstellen des Monatskalender-Steuerelements

Wie im Monatskalender-Steuerelement erstellt wird, hängt davon ab, ob Sie mithilfe des Steuerelements in einem Dialogfeld oder erstellen es in einer nicht-Dialogfenster.

### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>Verwenden von CMonthCalCtrl direkt in einem Dialogfeld

1. Der Dialog-Editor fügen Sie einem Monatskalender-Steuerelement hinzu, um der Dialogfeldvorlagen-Ressource. Geben Sie die Steuerelement-ID.

1. Geben Sie alle Formate, die erforderlich sind, verwenden das Dialogfeld "Eigenschaften", der im Monatskalender-Steuerelement.

1. Verwenden der [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md) zum Hinzufügen einer Membervariablen des Typs [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) mit der Eigenschaft des Steuerelements. Sie können diesen Member Aufrufen `CMonthCalCtrl` Memberfunktionen.

1. Verwendet im Eigenschaftenfenster in Handlerfunktionen in die Dialogfeldklasse zuordnen, für die Month Calendar-Steuerelement Benachrichtigungen angezeigt werden, behandeln müssen (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

1. In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie ggf. Weitere Formate für die `CMonthCalCtrl` Objekt.

### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>Zum Verwenden von CMonthCalCtrl in einem nicht-Dialogfenster

1. Definieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.

1. Aufrufen des Steuerelements [erstellen](../mfc/reference/cmonthcalctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so frühzeitig wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler-Funktion (Wenn Sie sind Erstellen von Unterklassen für das Steuerelement). Legen Sie die Formate für das Steuerelement.

## <a name="see-also"></a>Siehe auch

[Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

