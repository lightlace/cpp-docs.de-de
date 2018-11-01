---
title: Wortumbrüche in RichEdit-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
ms.openlocfilehash: efe4a0a2c06c14d913d43c51d1f0100f27c6a537
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632595"
---
# <a name="word-breaks-in-rich-edit-controls"></a>Wortumbrüche in RichEdit-Steuerelementen

Ein Rich-edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) Ruft eine Funktion, die eine "Word Break-Prozedur" wird aufgerufen, um Umbrüche zwischen Wörtern zu suchen und zu bestimmen, wo er Zeilen umbrochen kann. Das Steuerelement verwendet diese Informationen beim Ausführen von Vorgängen für Zeilenumbruch und bei der Verarbeitung der Tastenkombinationen STRG + nach-links- und STRG + nach-rechts. Eine Anwendung kann senden Nachrichten an ein rich-Edit-Steuerelement ersetzt die standardmäßige Wortumbruch Prozedur, zum Abrufen von Informationen von wortumbruchprobleme in Verbindung, und um zu bestimmen, was ein angegebenes Zeichen Zeile liegt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

