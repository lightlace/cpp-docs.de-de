---
title: Formatieren von Zeichen in RichEdit-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: a7467f9cd6a14dc6dfc2c03b6eb35f71802454fb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268641"
---
# <a name="character-formatting-in-rich-edit-controls"></a>Formatieren von Zeichen in RichEdit-Steuerelementen

Können Sie Memberfunktionen des rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) zum Formatieren von Zeichen und Formatierungsinformationen abzurufen. Für Zeichen Sie können angeben, Schriftart, Größe, Farbe und Effekte wie z. B. fett, kursiv und geschützt.

Sie können die zeichenformatierung mit Anwenden der [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) und [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) Memberfunktionen. Um das aktuelle Zeichen, die Formatierung für den ausgewählten Text zu ermitteln, verwenden die [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) Member-Funktion. Die [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) Struktur mit dieser Memberfunktionen verwendet, um Zeichenattribute anzugeben. Eines der wichtigen Member von **CHARFORMAT** ist **DwMask**. In `SetSelectionCharFormat` und `SetWordCharFormat`, **DwMask** gibt an, welche Zeichenattribute durch Aufrufen der Funktion festgelegt werden sollen. `GetSelectionCharFormat` meldet die Attribute des ersten Zeichens in der Auswahl. **DwMask** gibt die Attribute, die in die Auswahl konsistent sind.

Sie können auch abrufen und Festlegen der "standardzeichenformatierung," Dies ist die Formatierung auf nachfolgend eingefügten Zeichen angewendet. Beispielsweise ist, wenn eine Anwendung, das Standardzeichen festlegt fett formatieren, und der Benutzer dann ein Zeichen gibt, das Zeichen fett formatiert. Verwenden Sie zum Abrufen und Festlegen der standardzeichenformatierung, die [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) und [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) Memberfunktionen.

Das Zeichenattribut "protected" ändert sich nicht auf die Darstellung von Text aus. Wenn der Benutzer versucht, geschützten Text ändern, wird ein rich-Edit-Steuerelement sendet das übergeordnete Fenster eine **EN_PROTECTED durch** -benachrichtigungsmeldung und das übergeordnete Fenster, das erlauben oder verhindern die Änderung zu ermöglichen. Um diese Benachrichtigung zu erhalten, müssen Sie es mit aktivieren die [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) Member-Funktion. Weitere Informationen zu der Ereignismaske, finden Sie unter [Benachrichtigungen von einem RichEdit-Steuerelement](../mfc/notifications-from-a-rich-edit-control.md)weiter unten in diesem Thema.

Vordergrundfarbe ist ein Zeichenattribut, aber die Hintergrundfarbe ist eine Eigenschaft des rich-Edit-Steuerelements. Verwenden Sie zum Festlegen der Hintergrundfarbe der [Memberfunktion SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
