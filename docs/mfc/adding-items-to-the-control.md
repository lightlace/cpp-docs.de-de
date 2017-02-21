---
title: "Hinzuf&#252;gen von Elementen zum Steuerelement | Microsoft Docs"
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
  - "CListCtrl-Klasse, Hinzufügen von Elementen"
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Hinzuf&#252;gen von Elementen zum Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um Elemente dem Listensteuerelement \([Verwendung](../mfc/reference/clistctrl-class.md)\) hinzuzufügen, rufen Sie verschiedene Versionen der Memberfunktion [InsertItem](../Topic/CListCtrl::InsertItem.md), je nachdem welche Informationen Sie verfügen.  Eine Version verwendet [LV\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) eine Struktur, die Sie vorbereiten.  Da die `LV_ITEM`\-Struktur zahlreiche Member enthält, haben Sie eine umfassendere Kontrolle Attributen des Listensteuerelementelements.  
  
 Zwei wichtige Member \(hinsichtlich der Berichtsansicht\) der `LV_ITEM`\-Struktur sind `iItem` und `iSubItem` müssen Member.  Der `iItem`\-Member ist der nullbasierte Index des Elements, das die Struktur verweist und der Member `iSubItem` ist der einsbasierte Index eines Unterelements oder Null, wenn die Struktur Informationen über ein Element enthält.  Mit diesen zwei Membern bestimmen Sie, pro Element, und der Wert von Unterelementinformationen, die angezeigt wird, wenn das Listensteuerelement in der Berichtsansicht ist.  Weitere Informationen finden Sie unter [CListCtrl::SetItem](../Topic/CListCtrl::SetItem.md).  
  
 Zusätzliche Member geben den Text des Elements, dem Symbol, den Zustand und den Elementdaten an. "Elementdaten" sind ein von der Anwendung definierter Wert, der einem Listenansichtelement zugeordnet ist.  Weitere Informationen zum `LV_ITEM`\-Struktur, finden Sie unter [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md).  
  
 Andere Versionen von `InsertItem` akzeptieren eine oder mehrere Aufhebungen separates beschränkt, entsprechend Member `LV_ITEM` in der Struktur und ermöglicht, um nur Member zu initialisieren, die Sie unterstützen möchten.  Im Allgemeinen verwaltet das Listensteuerelement Speicher für Listenelemente, Sie können jedoch einige der Informationen in der Anwendung, mit der "Rückrufelemente stattdessen speichern." Weitere Informationen finden Sie in diesem Thema unter [Rückruf\-Elemente und die Rückruf\-Maske](../mfc/callback-items-and-the-callback-mask.md) und [Rückruf\-Elemente und die Rückruf\-Maske](http://msdn.microsoft.com/library/windows/desktop/bb774736) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter [Hinzufügen von Listenansichtelementen und von Unterelementen](http://msdn.microsoft.com/library/windows/desktop/bb774736).  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)