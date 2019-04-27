---
title: Formatieren von Absätzen in RichEdit-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: baee4863bee9b96e7a850e70b8f13388f69b41cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218831"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Formatieren von Absätzen in RichEdit-Steuerelementen

Können Sie Memberfunktionen des rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) zum Formatieren von Absätzen und zum Abrufen von Informationen über die Formatierung. Absatz Formatierungsattribute enthalten Ausrichtung, Registerkarten, Einzügen und Aufzählungszeichen.

Sie können mithilfe von Formatieren von Absätzen Anwenden der [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) Member-Funktion. Verwenden Sie zum Bestimmen des aktuellen Absatzes, für den markierten Text Formatieren der [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) Member-Funktion. Die [ABSATZFORMAT](/windows/desktop/api/richedit/ns-richedit-_paraformat) Struktur mit dieser Memberfunktionen verwendet, um Absatzattribute anzugeben. Eines der wichtigen Member von **ABSATZFORMAT** ist *DwMask*. In `SetParaFormat`, *DwMask* gibt an, welche Absatzattribute durch Aufrufen der Funktion festgelegt werden sollen. `GetParaFormat` meldet die Attribute des ersten Absatzes in der Auswahl. *DwMask* gibt die Attribute, die in die Auswahl konsistent sind.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
