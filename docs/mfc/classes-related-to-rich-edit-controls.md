---
title: Klassen im Zusammenhang mit RichEdit-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], and CRichEditItem
- CRichEditCtrl class [MFC], related classes
- CRichEditDoc class [MFC], Rich Edit controls
- rich edit controls [MFC], classes related to
- classes [MFC], related to rich edit controls
- rich edit controls [MFC], and CRichEditView
- CRichEditCtrlItem class and CRichEditCtrl
- rich edit controls [MFC], and CRichEditDoc
- CRichEditView class [MFC], and CRichEditCtrl
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
ms.openlocfilehash: 92134d0bd4d02bff7aeadd5e9ca7438c61de3bec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586159"
---
# <a name="classes-related-to-rich-edit-controls"></a>Klassen im Zusammenhang mit RichEdit-Steuerelementen

Die [CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) Klassen bieten die Funktionalität des rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) im Kontext der MFC Dokument-/Ansichtarchitektur. `CRichEditView` verwaltet den Text und Formatierung Merkmal des Texts. `CRichEditDoc` verwaltet die Liste der OLE-Client-Elemente, die in der Ansicht sind. `CRichEditCntrItem` Stellt die Container-Seite, auf das Client-OLE-Element. So ändern Sie den Inhalt einer `CRichEditView`, verwenden Sie [CRichEditView:: GetRichEditCtrl](../mfc/reference/cricheditview-class.md#getricheditctrl) beim Zugriff auf den Rich-edit-Steuerelement.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

