---
title: "Verwenden von CToolTipCtrl zum Erstellen und Bearbeiten eines CToolTipCtrl-Objekts"
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
  - "CToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl-Klasse, Verwenden"
  - "QuickInfos [C++], Erstellen"
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von CToolTipCtrl zum Erstellen und Bearbeiten eines CToolTipCtrl-Objekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Folgenden ein Beispiel aus der [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) verwenden:  
  
### Um ein CToolTipCtrl erstellen und bearbeiten  
  
1.  Erstellen Sie das `CToolTipCtrl`\-Objekt.  
  
2.  Rufen Sie [Erstellen](../Topic/CToolTipCtrl::Create.md) auf, um die Windows\-QuickInfogemeinsame allgemeinen ToolTip\-Steuerelement zu erstellen und auf das Objekt `CToolTipCtrl` anzufügen.  
  
3.  Rufen Sie [AddTool](../Topic/CToolTipCtrl::AddTool.md) auf, um ein Tool mit dem ToolTip\-Steuerelement zu registrieren, damit die Informationen, die in der QuickInfo gespeichert werden, angezeigt werden, wenn der Cursor auf dem Tool ist.  
  
4.  Rufen Sie [SetToolInfo](../Topic/CToolTipCtrl::SetToolInfo.md) auf, um die Informationen festzulegen, die eine QuickInfo für ein Tool enthält.  
  
5.  Rufen Sie [SetToolRect](../Topic/CToolTipCtrl::SetToolRect.md) auf, um ein neues umschließende Rechteck für ein Tool festzulegen.  
  
6.  Rufen Sie [HitTest](../Topic/CToolTipCtrl::HitTest.md) auf, um einen Punkt zu testen, um zu bestimmen, ob er innerhalb des umgebenden Rechtecks des angegebenen Tools ist und rufen Sie wenn ja Informationen zum Tool ab.  
  
7.  Rufen Sie [GetToolCount](../Topic/CToolTipCtrl::GetToolCount.md) auf, um eine der Anzahl Tools abzurufen, die dem ToolTip\-Steuerelement registriert werden.  
  
## Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)