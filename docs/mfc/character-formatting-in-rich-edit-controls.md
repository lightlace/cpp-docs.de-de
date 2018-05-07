---
title: Formatieren von Zeichen in RichEdit-Steuerelementen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c02165635e8715c1fcac28b9fbee72612b72c1f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="character-formatting-in-rich-edit-controls"></a>Formatieren von Zeichen in RichEdit-Steuerelementen
Können Sie Memberfunktionen des rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) zum Formatieren von Zeichen und Formatierungsinformationen abzurufen. Für Zeichen d. h., Sie können angeben, Schriftart, Größe, Farbe und Effekte wie fett, kursiv und geschützt.  
  
 Sie können die Formatierung mit Anwenden der [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) und [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) Memberfunktionen. Das aktuelle Zeichen für den ausgewählten Text formatieren ermitteln Sie mithilfe der [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) Memberfunktion. Die [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur wird mit diesen Memberfunktionen verwendet, um Zeichenattribute angeben. Eine der wichtigen Member der **CHARFORMAT** ist **DwMask**. In `SetSelectionCharFormat` und `SetWordCharFormat`, **DwMask** gibt an, welche Zeichenattribute durch Aufrufen der Funktion festgelegt werden. `GetSelectionCharFormat` meldet die Attribute des ersten Zeichens in der Auswahl. **DwMask** gibt die Attribute, die gesamte Auswahl konsistent sind.  
  
 Sie können auch abrufen und Festlegen der "Zeichen standardformatierung," die Formatierung für alle anschließend eingefügten Zeichen ist. Beispielsweise ist, wenn eine Anwendung des Standardzeichensatzes festlegt fett formatieren, und der Benutzer wird dann ein Zeichen eingibt, dieses Zeichen fett. Verwenden Sie zum Abrufen und zum Standard Zeichen Formatierung festlegen, die [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) und [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) Memberfunktionen.  
  
 Das Zeichenattribut "protected" ändert sich nicht auf die Darstellung von Text aus. Wenn der Benutzer versucht, geschützten Text zu ändern, sendet ein rich-Edit-Steuerelement das übergeordnete Fenster eine **EN_PROTECTED durch** benachrichtigungsmeldung, sodass das übergeordnete Fenster das erlauben oder Verhindern der Änderung. Um diese Benachrichtigung empfangen zu können, müssen Sie es mit aktivieren die [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) Memberfunktion. Weitere Informationen zu den Ereignismaske, finden Sie unter [Benachrichtigungen von einem RichEdit-Steuerelement](../mfc/notifications-from-a-rich-edit-control.md)weiter unten in diesem Thema.  
  
 Vordergrundfarbe ist ein Zeichenattribut, aber die Hintergrundfarbe ist eine Eigenschaft des rich-Edit-Steuerelements. Verwenden Sie zum Festlegen der Hintergrundfarbe der [Memberfunktion SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

