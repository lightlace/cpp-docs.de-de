---
title: "Klassen im Zusammenhang mit RichEdit-Steuerelementen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], bezogen auf Rich Edit-Steuerelemente"
  - "CRichEditCtrl-Klasse, verwandte Klassen"
  - "CRichEditCtrlItem-Klasse und CRichEditCtrl"
  - "CRichEditDoc-Klasse, Rich Edit-Steuerelemente"
  - "CRichEditView-Klasse, und CRichEditCtrl"
  - "Rich-Edit-Steuerelemente, und CRichEditDoc"
  - "Rich-Edit-Steuerelemente, und CRichEditItem"
  - "Rich-Edit-Steuerelemente, und CRichEditView"
  - "Rich-Edit-Steuerelemente, Klassen bezogen auf"
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Klassen im Zusammenhang mit RichEdit-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CRichEditView](../mfc/reference/cricheditview-class.md), [CRichEditDoc](../mfc/reference/cricheditdoc-class.md) und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)\-Klassen stellen die Funktionalität des Rich\-Edit\-Steuerelements \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) im Kontext Dokument\-\/Ansichtarchitektur MFC bereit.  `CRichEditView` verwaltet das Text\- und Formatierungseigenschaft des Texts bei.  `CRichEditDoc` führt die Liste der OLE\-Clientelementen, die in der Ansicht sind.  `CRichEditCntrItem` bietet ContainerSeitenzugang zum OLE\-Clientelement.  Um den Inhalt von `CRichEditView` zu ändern, verwenden Sie [CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md) um auf das zugrunde liegende Rich\-Edit\-Steuerelement zuzugreifen.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)