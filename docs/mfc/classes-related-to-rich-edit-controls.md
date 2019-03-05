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
ms.openlocfilehash: 349a8b5c26b7260c9af496d0f4a3a997ee753020
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258098"
---
# <a name="classes-related-to-rich-edit-controls"></a>Klassen im Zusammenhang mit RichEdit-Steuerelementen

Die [CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) Klassen bieten die Funktionalität des rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) im Kontext der MFC Dokument-/Ansichtarchitektur. `CRichEditView` verwaltet den Text und Formatierung Merkmal des Texts. `CRichEditDoc` verwaltet die Liste der OLE-Client-Elemente, die in der Ansicht sind. `CRichEditCntrItem` Stellt die Container-Seite, auf das Client-OLE-Element. So ändern Sie den Inhalt einer `CRichEditView`, verwenden Sie [CRichEditView:: GetRichEditCtrl](../mfc/reference/cricheditview-class.md#getricheditctrl) beim Zugriff auf den Rich-edit-Steuerelement.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
