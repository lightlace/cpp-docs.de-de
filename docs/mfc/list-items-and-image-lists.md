---
title: "Listenelemente und Bildlisten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList-Klasse, und Listenelemente"
  - "CListCtrl-Klasse, Bilderlisten"
  - "Bilderlisten [C++], Listenelemente"
  - "Listenelemente, Bilderlisten"
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Listenelemente und Bildlisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein "Element" in einem Listensteuerelement \([Verwendung](../mfc/reference/clistctrl-class.md)\) besteht ein Symbol, eine Bezeichnung und möglicherweise aus anderen Informationen \(in "Unterelementen"\).  
  
 Die Symbole für Listensteuerelementelemente werden in den Bildlisten enthalten.  Mit einer Bildliste enthält Symbole die an, die in der Symbolen verwendet werden.  Ein zweites, optional, Bildliste enthält kleinere Versionen der gleichen Symbole für andere Ansichten des Steuerelements.  Eine dritte optionale Liste enthält "Bundesstaat " \- Bilder, z Kontrollkästchen, für die Anzeige vor kleinen Symbolen in bestimmten Ansichten.  Eine vierte optionale Liste Bilder enthält, die in einzelnen Kopfzeilenelementen des Listensteuerelements angezeigt werden.  
  
> [!NOTE]
>  Wenn ein ListView\-Steuerelement mit dem Format `LVS_SHAREIMAGELISTS` erstellt wird, sind Sie das Zerstören der Bildlisten zuständig, wenn sie nicht mehr in Gebrauch sind.  Geben Sie dieses Format an, wenn Sie die gleichen Bildlisten zu mehreren Listenansicht\-Steuerelementen zuweisen; Andernfalls versucht möglicherweise mehr als ein Steuerelement, dieselbe Bildliste zu zerstören.  
  
 Weitere Informationen über Listenelemente, finden Sie unter [Listenansichts\-Bildlisten](http://msdn.microsoft.com/library/windows/desktop/bb774736) und [Elemente und Unterelemente](http://msdn.microsoft.com/library/windows/desktop/bb774736) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Siehe auch Klasse [CImageList](../mfc/reference/cimagelist-class.md) in der *MFC\-Referenz* und [Verwenden CImageList](../mfc/using-cimagelist.md) dieser Familie von Artikeln.  
  
 Um ein Listensteuerelement zu erstellen, müssen Sie die zu verwendende Bildlisten stellen wenn Sie neue Elemente in die Liste eingefügt.  Im folgenden Beispiel wird diese Prozedur, in der `m_pImagelist` ein Zeiger vom Typ `CImageList` und `m_listctrl` ein `CListCtrl` \- Datenmember ist.  
  
 [!CODE [NVC_MFCControlLadenDialog#19](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#19)]  
  
 Wenn Sie nicht planen, Symbole in der Listenansicht oder in Listensteuerelement anzuzeigen, benötigen Sie keine Bildlisten.  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)