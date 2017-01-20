---
title: "CTreeCtrl im Vergleich mit CTreeView"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CTreeCtrl"
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl-Klasse, kontra CTreeView-Klasse"
  - "CTreeView-Klasse, kontra CTreeCtrl-Klasse"
  - "Struktursteuerelemente, und Strukturansicht"
  - "Strukturansicht-Steuerelemente"
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeCtrl im Vergleich mit CTreeView
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC stellt zwei Klassen Tree\-Steuerelementen, die gekapselt werden: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) und [CTreeView](../mfc/reference/ctreeview-class.md).  Jede Klasse ist in verschiedenen Situationen nützlich.  
  
 Verwenden Sie `CTreeCtrl`, wenn Sie ein einfaches Steuerelement des untergeordneten Fensters müssen; beispielsweise in einem Dialogfeld.  Sie können insbesondere die `CTreeCtrl`, wenn sie andere untergeordnete Steuerelemente im Fenster gibt, wie in einem typischen Dialogfeld verwendet werden.  
  
 Verwenden Sie `CTreeView`, wenn das Tree\-Steuerelement wie ein Ansichtsfenster in der Dokument\-\/Ansichtarchitektur sowie in einem sich Strukturansicht soll.  `CTreeView` nimmt den gesamten Clientbereich eines Rahmenfensters oder des Splitterfensters.  Es wird automatisch angepasst, wenn sein übergeordnetes Fenster Größe geändert wird, und es kann Befehlsmeldungen von Menüs, von Zugriffstasten und Symbolleisten verarbeiten.  Da eine Strukturansicht die Daten enthält, die erforderlich sind, die Struktur anzuzeigen, muss das entsprechende Dokumentobjekt nicht schwierig \- Sie können [CDocument](../mfc/reference/cdocument-class.md) als Dokumenttyp in der Normal\-Vorlage sogar.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)