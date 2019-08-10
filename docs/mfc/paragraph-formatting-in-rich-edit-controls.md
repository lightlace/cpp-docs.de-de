---
title: Formatieren von Absätzen in RichEdit-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: 0988e7940c8d8947b86e97a35d71586f8f5c316a
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916375"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Formatieren von Absätzen in RichEdit-Steuerelementen

Sie können Element Funktionen des Rich Edit-Steuer Elements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) zum Formatieren von Absätzen und zum Abrufen von Formatierungsinformationen verwenden. Die Attribute für die Absatz Formatierung umfassen Ausrichtung, Tabstopps, Einzüge und Nummerierung.

Sie können die Absatz Formatierung mithilfe der [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) -Member-Funktion anwenden. Um die aktuelle Absatz Formatierung für den ausgewählten Text zu ermitteln, verwenden Sie die [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) -Member-Funktion. Die [paraformat](/windows/desktop/api/richedit/ns-richedit-paraformat) -Struktur wird mit diesen Element Funktionen verwendet, um Absatz Attribute anzugeben. Eines der wichtigen Member von " **paraformat** " ist " *dwMask*". In `SetParaFormat`gibt *dwMask* an, welche Absatz Attribute von diesem Funktionsbefehl festgelegt werden. `GetParaFormat`meldet die Attribute des ersten Absatzes in der Auswahl. *dwMask* gibt die Attribute an, die in der gesamten Auswahl einheitlich sind.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
