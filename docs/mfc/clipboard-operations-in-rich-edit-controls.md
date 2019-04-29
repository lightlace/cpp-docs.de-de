---
title: Zwischenablageoperationen in RichEdit-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
ms.openlocfilehash: 882c589d0d25b54650affa7fd41f916ecf6097d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327105"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Zwischenablageoperationen in RichEdit-Steuerelementen

Ihre Anwendung kann den Inhalt der Zwischenablage in eine rich-Edit-Steuerelement einfügen ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) mit den am besten verfügbaren das Format der Zwischenablage oder ein bestimmtes Zwischenablageformat. Sie können auch bestimmen, ob ein rich-Edit-Steuerelement eine das Format der Zwischenablage einfügen kann.

Können Sie kopieren oder Ausschneiden den Inhalt der aktuellen Auswahl mithilfe der [Kopie](../mfc/reference/cricheditctrl-class.md#copy) oder [Ausschneiden](../mfc/reference/cricheditctrl-class.md#cut) Member-Funktion. Sie können auf ähnliche Weise den Inhalt der Zwischenablage in eine rich-Edit-Steuerelement einfügen, mit der [einfügen](../mfc/reference/cricheditctrl-class.md#paste) Member-Funktion. Das Steuerelement fügt das erste verfügbare Format, das er erkennt, d. h., vermutlich der am häufigsten aussagekräftigen Format.

Um ein bestimmtes Zwischenablageformat einzufügen, können Sie die [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial) Member-Funktion. Diese Funktion ist nützlich für Anwendungen mit einem Befehl Inhalte einfügen, der dem Benutzer ermöglicht, wählen Sie das Format der Zwischenablage. Sie können die [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) Memberfunktion, um zu bestimmen, ob es sich bei ein bestimmtes Format, die vom Steuerelement erkannt wird.

Sie können auch `CanPaste` zu bestimmen, ob alle verfügbaren Format der Zwischenablage von einem rich-Edit-Steuerelement erkannt wird. Diese Funktion ist nützlich, in der `OnInitMenuPopup` Handler. Eine Anwendung kann aktiviert oder graue der Befehl "Einfügen", je nachdem, ob das Steuerelement ein verfügbares Format einfügen kann.

Rich-Edit-Steuerelemente registrieren zwei Zwischenablageformate: Rich-Text-Format und ein Format namens RichEdit-Text und Objekte. Eine Anwendung kann diese Formate registrieren, indem Sie mit der [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) ordnungsgemäß verwendet werden, Angeben der **Werte CF_RTF** und **CF_RETEXTOBJ angegeben werden müssen** Werte.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
