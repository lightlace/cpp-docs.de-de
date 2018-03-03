---
title: Klassen im Zusammenhang mit RichEdit-Steuerelementen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8373435f1f97b6b2038e5769c853d521b906715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="classes-related-to-rich-edit-controls"></a>Klassen im Zusammenhang mit RichEdit-Steuerelementen
Die [CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md), und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) Klassen bieten die Funktionalität des rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) im Kontext der MFC Dokument-/ Ansichtarchitektur. `CRichEditView`der Text und Formatierung Texteigenschaft beibehalten. `CRichEditDoc`verwaltet die Liste der OLE-Client-Elemente, die in der Ansicht sind. `CRichEditCntrItem`OLE-Clientelement erläutert Container-Seite. Zum Ändern des Inhalts von einem `CRichEditView`, verwenden Sie [CRichEditView:: GetRichEditCtrl](../mfc/reference/cricheditview-class.md#getricheditctrl) zum Zugriff auf die zugrunde liegenden Rich-edit-Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

