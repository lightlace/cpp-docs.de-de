---
title: Die aktuelle Auswahl in einem RichEdit-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
ms.openlocfilehash: 4516c4506419169ac3ab284e6c59cae71595be59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241800"
---
# <a name="current-selection-in-a-rich-edit-control"></a>Die aktuelle Auswahl in einem RichEdit-Steuerelement

Der Benutzer Text in einem rich-Edit-Steuerelement auswählen kann ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) mithilfe der Maus oder der Tastatur. Die aktuelle Auswahl ist der Bereich der markierten Zeichen oder die Position der Einfügemarke, wenn keine Zeichen ausgewählt werden. Eine Anwendung kann erfahren Sie mehr über die aktuelle Auswahl, die aktuelle Auswahl festlegen, bestimmen den Änderungen der aktuellen Auswahl, und anzeigen oder Ausblenden der Auswahl beim markieren.

Verwenden Sie zum Bestimmen der aktuellen Auswahl in einem rich-Edit-Steuerelement die [Memberfunktion GetSel](../mfc/reference/cricheditctrl-class.md#getsel) Member-Funktion. Verwenden Sie zum Festlegen der aktuellen Auswahl der [Memberfunktion SetSel](../mfc/reference/cricheditctrl-class.md#setsel) Member-Funktion. Die [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) Struktur mit diesen Funktionen verwendet, um einen Bereich von Zeichen anzugeben. Um Informationen über den Inhalt der aktuellen Auswahl abzurufen, können Sie die [Memberfunktion GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype) Member-Funktion.

Standardmäßig wird ein rich-Edit-Steuerelement zeigt und blendet Sie aus der Markierung der erhält und den Fokus verliert. Sie können ein- oder die Markierung der jederzeit ausblenden, indem die [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) Member-Funktion. Beispielsweise kann eine Anwendung eine Meldungssuche (Dialogfeld), um nach Text in einem rich-Edit-Steuerelement suchen bereitstellen. Die Anwendung möglicherweise übereinstimmenden Text auswählen, ohne das Dialogfeld zu schließen, er muss in diesem Fall verwenden `HideSelection` markieren.

Rufen Sie den markierten Text in einem rich-Edit-Steuerelement mit dem [Memberfunktion GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext) Member-Funktion. Der Text wird in das angegebene Zeichenarray kopiert. Sie müssen sicherstellen, dass das Array groß genug für den markierten Text und ein abschließendes Null-Zeichen ist.

Sie können nach einer Zeichenfolge in einem rich-Edit-Steuerelement suchen, mit der [FindText](../mfc/reference/cricheditctrl-class.md#findtext) Memberfunktion die [FINDTEXTEX](/windows/desktop/api/richedit/ns-richedit-_findtextexa) Struktur, die diese Funktion gibt an, der Bereich des Texts zu suchen und die zu suchende Zeichenfolge. Sie können diese Optionen auch angeben, als gibt an, ob der Suche die Groß-/Kleinschreibung beachtet werden.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
