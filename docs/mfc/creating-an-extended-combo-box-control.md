---
title: Erstellen eines erweiterten Kombinationsfeld-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: 87e2e1cd3c29ba838a17c24ece4a89adda21db0c
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907726"
---
# <a name="creating-an-extended-combo-box-control"></a>Erstellen eines erweiterten Kombinationsfeld-Steuerelements

Wie das erweiterte Kombinations Feld-Steuerelement erstellt wird, hängt davon ab, ob Sie das Steuerelement in einem Dialogfeld verwenden oder es in einem nicht Dialogfeld erstellen.

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>So verwenden Sie CComboBoxEx direkt in einem Dialogfeld

1. Fügen Sie im Dialog-Editor der Dialogfeld Vorlagen Ressource ein erweitertes Kombinations Feld-Steuerelement hinzu. Gibt die Steuerelement-ID an.

1. Geben Sie alle Stile an, die im Dialogfeld "Eigenschaften" des erweiterten Kombinations Feld-Steuer Elements erforderlich sind.

1. Verwenden Sie den [Assistenten zum Hinzufügen](../ide/adding-a-member-variable-visual-cpp.md) von Element Variablen, um eine Member-Variable vom Typ [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) mit der Control-Eigenschaft hinzuzufügen. Sie können diesen Member verwenden, um `CComboBoxEx` Member-Funktionen aufzurufen.

1. Verwenden Sie den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um Handlerfunktionen in der Dialogfeld Klasse für alle erweiterten Kombinations Feld-Steuerelement-Benachrichtigungs Meldungen zuzuordnen, die Sie behandeln müssen (siehe zuordnen [von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

1. Legen Sie in [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)alle zusätzlichen Stile für das `CComboBoxEx` -Objekt fest.

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>So verwenden Sie "CComboBoxEx" in einem nicht-Dialogfenster

1. Definieren Sie das Steuerelement in der Ansicht oder in der Fenster Klasse.

1. Rufen Sie die [Create](../mfc/reference/ctabctrl-class.md#create) Member-Funktion des Steuer Elements (möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)) auf, möglicherweise so früh wie die [OnCreate](../mfc/reference/cwnd-class.md#oncreate) -Handlerfunktion des übergeordneten Fensters. Legen Sie die Stile für das-Steuerelement fest.

## <a name="see-also"></a>Siehe auch

[Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
