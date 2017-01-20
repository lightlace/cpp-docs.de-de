---
title: "Listensteuerelement und Listenansichtsteuerelement"
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
  - "CListCtrl-Klasse, und CListView"
  - "CListView-Klasse, und CListCtrl"
  - "List-Steuerelemente, Listenansicht"
  - "Listenansichten"
  - "Ansichten, Liste und Listensteuerelement"
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Listensteuerelement und Listenansichtsteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zur Vereinfachung kapselt MFC das Listensteuerelement auf zwei Arten.  Listensteuerelemente können Sie verwenden:  
  
-   Direkt durch Einbettung eines [Verwendung](../mfc/reference/clistctrl-class.md)\-Objekts in einer Dialogfeldklasse.  
  
-   Indirekte Verwendung mit der Klasse [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView` vereinfacht, ein Listensteuerelement mit der MFC\-Dokument\-\/Ansichtsarchitektur integrieren und kapselt das Steuerelement viel, während ein Bearbeitungssteuerelement kapselt: [CEditView](../mfc/reference/ceditview-class.md) das Steuerelement füllt die gesamte Oberfläche einer MFC\-Ansicht aus. \(Die Ansicht *ist* das Steuerelement, Umwandlung in `CListView`.\)  
  
 Ein `CListView`\-Objekt erbt von [CCtrlView](../mfc/reference/cctrlview-class.md) und von den Basisklassen und fügt eine Memberfunktion hinzu, um das Steuerelement der zugrunde liegenden Liste abzurufen.  Verwenden Sie Ansichtsmember, um mit der Ansicht als Ansicht zu arbeiten.  Verwenden Sie die [GetListCtrl](../Topic/CListView::GetListCtrl.md)\-Memberfunktion, um zu Memberfunktionen des Listensteuerelements zu erhalten.  Verwenden Sie diese Member:  
  
-   Hinzufügen, Löschen oder bearbeiten Sie "Arbeitsaufgaben" in der Liste.  
  
-   Festgelegt oder rufen Sie Listensteuerelementattribute ab.  
  
 Um einen Verweis auf `CListCtrl` abzurufen, das `CListView` zugrunde liegt, rufen Sie `GetListCtrl` in der Listenansichtsklasse auf:  
  
 [!CODE [NVC_MFCListView#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCListView#4)]  
  
 In diesem Thema werden beide Methoden, das Listensteuerelement verwenden.  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)