---
title: "Einstellungen f&#252;r das QuickInfo-Steuerelement | Microsoft Docs"
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
  - "Quickinfos [C++], aktivieren"
  - "CToolTipCtrl-Klasse, Einstellungen"
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Einstellungen f&#252;r das QuickInfo-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können das QuickInfo\-Steuerelement \([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)\) entweder als aktiv oder als inaktiv festlegen. Wenn Sie es als aktiv festlegen, wird das QuickInfo\-Steuerelement angezeigt, wenn Sie den Cursor auf einem Tool platzieren. Wenn Sie es als inaktiv festlegen, wird das QuickInfo\-Steuerelement auch dann nicht angezeigt, wenn sich der Cursor auf einem Tool befindet. Rufen Sie [Activate](../Topic/CToolTipCtrl::Activate.md) auf, um ein QuickInfo\-Steuerelement zu aktivieren oder deaktivieren.  
  
 Sie können die Anzeige eines aktiven QuickInfo\-Steuerelements, wenn sich der Cursor auf einem Tool befindet, mithilfe der Formatvorlage **TTS\_ALWAYSTIP** so festlegen, dass die Anzeige unabhängig vom Aktivierungszustand des besitzenden Fensters erfolgt. Wenn Sie dieses Formatvorlage nicht verwenden, wird das QuickInfo\-Steuerelement angezeigt, wenn das besitzende Fenster des Steuerelements aktiv ist, aber nicht, wenn es nicht aktiv ist.  
  
 Die meisten Anwendungen enthalten Symbolleisten mit Tools, die Menübefehlen entsprechen. Für solche Tools ist es sinnvoll, wenn im QuickInfo\-Steuerelement der gleiche Text wie im entsprechenden Menüelement angezeigt wird. Das System entfernt automatisch das kaufmännische Und\-Zeichen für die Tastenkombination \(&\) aus allen Zeichenfolgen, die an ein QuickInfo\-Steuerelement übergeben werden, es sei denn, das Steuerelement verwendet die Formatvorlage **TTS\_NOPREFIX**.  
  
## Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)