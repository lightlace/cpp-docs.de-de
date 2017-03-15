---
title: "Verwenden von Schieberegler-Steuerelementen | Microsoft Docs"
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
  - "CSliderCtrl-Klasse, Verwenden"
  - "Schieberegler-Steuerelemente"
  - "Schieberegler-Steuerelemente, Verwenden"
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Verwenden von Schieberegler-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typische Verwendung eines "Slider" \- Steuerelements entspricht dem Muster unten:  
  
-   Das Steuerelement wird erstellt.  Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, ist Erstellung automatisch, wenn das Dialogfeld erstellt wird. \(Sie sollten [CSliderCtrl](../mfc/reference/csliderctrl-class.md) einen Member in der Dialogfeldklasse haben, die für das Slider\-Steuerelement entspricht.\) Alternativ können Sie die Memberfunktion [Erstellen](../Topic/CSliderCtrl::Create.md) verwenden, um das Steuerelement als untergeordnetes Fenster eines jeden Fensters zu erstellen.  
  
-   Rufen Sie die verschiedenen Funktionen des festgelegten Members zum Festlegen von Werten für das Steuerelement auf.  Ändert, dass Sie die Include ausführen können, die die minimale und maximale Positionen für den Schieberegler festlegt, Teilstriche, zeichnet einen Auswahlbereich festgelegt und der Schieberegler neu angeordnet werden.  Für Steuerelemente in einem Dialogfeld, ist ein guter Zeitpunkt, dazu in der [OnInitDialog](../Topic/CDialog::OnInitDialog.md)\-Funktion des Dialogfelds.  
  
-   Wenn der Benutzer das Steuerelement verwendet, sendet es verschiedene Benachrichtigungsmeldungen.  Sie können den Schiebereglerwert vom Steuerelement extrahieren, indem Sie die Memberfunktion [GetPos](../Topic/CSliderCtrl::GetPos.md) aufrufen.  
  
-   Wenn Sie mit dem Steuerelement erreichen, müssen Sie sicherstellen, dass es ordnungsgemäß gelöscht wird.  Wenn das Schieberegler\-Steuerelement in einem Dialogfeld ist, werden diese und das `CSliderCtrl`\-Objekt automatisch zerstört.  Falls nicht, müssen Sie sicherstellen, dass das Steuerelement und das `CSliderCtrl`\-Objekt ordnungsgemäß gelöscht werden.  
  
## Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)