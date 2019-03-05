---
title: Benachrichtigungen von einem RichEdit-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: fcb1dda1d915dc13e01effed9ba99070b825a15e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274530"
---
# <a name="notifications-from-a-rich-edit-control"></a>Benachrichtigungen von einem RichEdit-Steuerelement

Benachrichtigung Nachrichten Bericht Ereignisse, die Auswirkungen auf eine Rich-edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Sie können durch das übergeordnete Fenster verarbeitet werden oder mithilfe von Reflektion Nachricht vom Rich edit-Steuerelement selbst. Rich-Edit-Steuerelemente unterstützen alle die Verwendung der Edit-Steuerelemente sowie einige zusätzliche Benachrichtigungsnachrichten erstellt werden. Sie können bestimmen, welche Benachrichtigungen ein rich-Edit-Steuerelement das übergeordnete Fenster sendet durch Festlegen der "Ereignismaske".

Verwenden Sie zum Festlegen der Ereignismaske für eine Rich--Steuerelement Edit die [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) Member-Funktion. Sie können die aktuelle Ereignismaske für ein Steuerelement mit RichEdit-Abrufen der [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) Member-Funktion.

In den folgenden Abschnitten Listen einige bestimmte Benachrichtigungen und deren Verwendung:

- EN_MSGFILTER durch Verarbeiten der Benachrichtigung EN_MSGFILTER können einer Klasse entweder das rich-Edit-Steuerelement oder das übergeordnete Fenster, die alle Tastatur- und Mauseingaben an das Steuerelement zu filtern. Der Ereignishandler kann verhindern, dass die Tastatur oder Maus-Nachricht verarbeitet wird, oder ändern Sie die Nachricht kann durch Ändern der angegebenen [MSGFILTER](/windows/desktop/api/richedit/ns-richedit-_msgfilter) Struktur.

- EN_PROTECTED durch Behandeln der EN_PROTECTED-Benachrichtigung erkennen, wenn der Benutzer versucht, geschützten Text zu ändern. Um einen Textbereich als geschützt zu markieren, können Sie die Auswirkungen der geschützten Zeichen festlegen. Weitere Informationen finden Sie unter [Zeichenformatierung in Rich-Edit-Steuerelemente](../mfc/character-formatting-in-rich-edit-controls.md).

- EN_DROPFILES Sie können den Benutzer auf Dateien in einem rich-Edit-Steuerelement löschen, indem Sie die Verarbeitung der benachrichtigungsmeldung EN_DROPFILES aktivieren. Das angegebene [ENDROPFILES](/windows/desktop/api/richedit/ns-richedit-_endropfiles) Struktur enthält Informationen zu den Dateien, die gelöscht wird.

- EN_SELCHANGE-Ereignis eine Anwendung kann erkennen, wenn die aktuelle Auswahl geändert wird, durch die Verarbeitung der benachrichtigungsmeldung EN_SELCHANGE-Ereignis. Gibt an, die Nachricht eine [SELCHANGE](/windows/desktop/api/richedit/ns-richedit-_selchange) Struktur mit Informationen über die neue Auswahl.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
