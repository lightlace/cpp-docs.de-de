---
title: "Bearbeiten des QuickInfo-Steuerelements | Microsoft Docs"
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
  - "CToolTipCtrl-Klasse, Bearbeiten von QuickInfo-Attributen"
  - "QuickInfos [C++], Attribute"
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Bearbeiten des QuickInfo-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CToolTipCtrl`\-Klasse stellt eine Gruppe Memberfunktionen, die unterschiedliche Attribute des `CToolTipCtrl`\-Objekts und des QuickInfo\-Fensters steuern.  
  
 Die ursprüngliche, das Popup und die reshow Dauer für die QuickInfo\-Fenster können durch Aufrufe von [GetDelayTime](../Topic/CToolTipCtrl::GetDelayTime.md) und [SetDelayTime](../Topic/CToolTipCtrl::SetDelayTime.md) festgelegt und abgerufen werden.  
  
 Ändern der Darstellung der QuickInfo\-Fenster mit den folgenden Features:  
  
-   [GetMargin](../Topic/CToolTipCtrl::GetMargin.md) und [SetMargin](../Topic/CToolTipCtrl::SetMargin.md) ruft ab und legt die Breite zwischen dem QuickInforahmen und den QuickInfo\-Text fest.  
  
-   [GetMaxTipWidth](../Topic/CToolTipCtrl::GetMaxTipWidth.md) und [SetMaxTipWidth](../Topic/CToolTipCtrl::SetMaxTipWidth.md) ruft ab und legt die maximale Breite des QuickInfo\-Fensters fest.  
  
-   [GetTipBkColor](../Topic/CToolTipCtrl::GetTipBkColor.md) und [SetTipBkColor](../Topic/CToolTipCtrl::SetTipBkColor.md) ruft ab und legt die Hintergrundfarbe des QuickInfo\-Fensters fest.  
  
-   [GetTipTextColor](../Topic/CToolTipCtrl::GetTipTextColor.md) und [SetTipTextColor](../Topic/CToolTipCtrl::SetTipTextColor.md) ruft ab und legt die Textfarbe des QuickInfo\-Fensters fest.  
  
 Damit das ToolTip\-Steuerelement von wichtigen Meldungen, wie **WM\_LBUTTONXXX** Meldungen benachrichtigt werden, müssen Sie die Meldungen für das ToolTip\-Steuerelement weitergeben.  Die beste Methode für dieses Relay ist, machen einen Aufruf von [CToolTipCtrl::RelayEvent](../Topic/CToolTipCtrl::RelayEvent.md), in der `PreTranslateMessage`\-Funktion des Besitzerfensters.  Im folgenden Beispiel wird eine andere Methode \(das ToolTip\-Steuerelement vorausgesetzt wird `m_ToolTip`\) aufgerufen:  
  
 [!CODE [NVC_MFCControlLadenDialog#41](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#41)]  
  
 Um ein QuickInfo\-Fenster sofort zu entfernen, rufen Sie die [pop](../Topic/CToolTipCtrl::Pop.md)\-Memberfunktion auf.  
  
## Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)