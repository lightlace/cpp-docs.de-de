---
title: "Headersteuerelement und Listensteuerelement"
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
  - "CHeaderCtrl-Klasse, mit CListCtrl"
  - "CListCtrl-Klasse, Headersteuerelemente"
  - "CListCtrl-Klasse, mit CHeaderCtrl"
  - "Steuerelemente [MFC], Header"
  - "Headersteuerelemente"
  - "Headersteuerelemente, Listensteuerelemente verwendet mit"
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Headersteuerelement und Listensteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In den meisten Fällen verwenden Sie das Header\-Steuerelement, das in einem [Verwendung](../mfc/reference/clistctrl-class.md) oder [CListView](../mfc/reference/clistview-class.md)\-Objekt eingebettet wird.  jedoch, es gibt jedoch Fälle, in denen ein separates Header\-Steuerelement\-Objekt, wie Bearbeiten von Daten erwünscht ist, angeordnet in Spalten oder in Zeilen, [CView](../mfc/reference/cview-class.md) abgeleitetes Objekt.  In diesen Fällen benötigen Sie größere Kontrolle über das Aussehen und Standardverhalten eines eingebetteten Header\-Steuerelements.  
  
 Im Allgemeinen Fall, dass ein Header\-Steuerelement Standard bereitstellen soll, Standardverhalten, sollten Sie [Verwendung](../mfc/reference/clistctrl-class.md) oder stattdessen [CListView](../mfc/reference/clistview-class.md) verwenden.  Verwenden Sie `CListCtrl`, wenn Sie die Funktionalität eines Standardheader\-steuerelements soll, eingebettet in einer Listenansichtsgemeinsamen allgemeinen ToolTip\-Steuerelement.  Verwenden Sie [CListView](../mfc/reference/clistview-class.md), wenn Sie die Funktionalität eines Standardheader\-steuerelements soll, eingebettet in einem Ansichtsobjekt.  
  
> [!NOTE]
>  Diese Steuerelemente umfassen nur ein integriertes Header\-Steuerelement, wenn das ListView\-Steuerelement mit dem Format `LVS_REPORT` erstellt wird.  
  
 In den meisten Fällen kann die Darstellung des eingebetteten Header\-Steuerelements geändert werden, indem die Stile des enthaltenden Listenansicht\-Steuerelements ändert.  Außerdem können Informationen zum das Header\-Steuerelement von Memberfunktionen des übergeordneten Listenansicht\-Steuerelements abgerufen.  Für die vollständige Steuerung und Zugriff, Attributen und Formaten des eingebetteten Header\-Steuerelements, wird empfohlen, dass ein Zeiger auf Header\-Steuerelement\-Objekt abgerufen wird.  
  
 Auf das eingebettete Header\-Steuerelement\-Objekt kann von **CListCtrl**  oder `CListView` mit einem Aufruf zugegriffen werden entweder zur jeweiligen `GetHeaderCtrl`\-Memberfunktion der Klasse.  Der folgende Code zeigt dies:  
  
 [!CODE [NVC_MFCControlLadenDialog#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#14)]  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden der Bildlisten mit Header\-Steuerelementen](../mfc/using-image-lists-with-header-controls.md)  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)