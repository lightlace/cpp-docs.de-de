---
title: Erstellen eines erweiterten Kombinationsfeld-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: d1e81664403f45a0a35cd24ceea16e1425b03403
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668766"
---
# <a name="creating-an-extended-combo-box-control"></a>Erstellen eines erweiterten Kombinationsfeld-Steuerelements

Wie die erweiterten Kombinationsfeld-Steuerelement erstellt wird, hängt davon ab, ob Sie mithilfe des Steuerelements in einem Dialogfeld oder erstellen es in einer nicht-Dialogfenster.

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>Verwenden von CComboBoxEx direkt in einem Dialogfeld

1. Der Dialog-Editor fügen Sie ein Erweitertes Kombinationsfeld-Steuerelement hinzu, um der Dialogfeldvorlagen-Ressource. Geben Sie die Steuerelement-ID.

1. Geben Sie alle Formate, die erforderlich sind, mithilfe des Dialogfelds "Eigenschaften" des erweiterten Kombinationsfeld-Steuerelements.

1. Verwenden der [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md) zum Hinzufügen einer Membervariablen des Typs [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) mit der Eigenschaft des Steuerelements. Sie können diesen Member Aufrufen `CComboBoxEx` Memberfunktionen.

1. Verwenden Sie das Fenster "Eigenschaften", um Handlerfunktionen in die Dialogfeldklasse für benachrichtigungsmeldungen des Registersteuerelements alle erweiterten Kombinationsfeld Feld zuzuordnen, behandelt werden müssen (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

1. In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie ggf. Weitere Formate für die `CComboBoxEx` Objekt.

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>Zum Verwenden von CComboBoxEx in einem nicht-Dialogfenster

1. Definieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.

1. Aufrufen des Steuerelements [erstellen](../mfc/reference/ctabctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so frühzeitig wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler-Funktion. Legen Sie die Formate für das Steuerelement.

## <a name="see-also"></a>Siehe auch

[Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

