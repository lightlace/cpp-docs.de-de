---
title: "Methoden zum Erstellen von QuickInfos"
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
  - "CToolTipCtrl-Klasse, Erstellen von QuickInfos"
  - "QuickInfos [C++], Erstellen"
  - "QuickInfos [C++], QuickInfo-Steuerelemente"
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Methoden zum Erstellen von QuickInfos
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC stellt drei Klassen, um das ToolTip\-Steuerelement zu erstellen und zu verwalten: [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) und [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md).  Die QuickInfomemberfunktionen in diesen Klassen binden die API des allgemeinen Windows\-Steuerelements ein.  Klasse `CToolBarCtrl` und die Klasse `CToolTipCtrl` von der `CWnd`\- Klasse abgeleitet.  
  
 `CWnd` stellt vier Memberfunktionen, um QuickInfos zu erstellen und zu verwalten: [EnableToolTips](../Topic/CWnd::EnableToolTips.md), [CancelToolTips](../Topic/CWnd::CancelToolTips.md), [FilterToolTipMessage](../Topic/CWnd::FilterToolTipMessage.md) und [OnToolHitTest](../Topic/CWnd::OnToolHitTest.md).  Siehe diese einzelnen Funktionen des Mitglieds weitere Informationen dazu, wie diese QuickInfo implementieren.  
  
 Wenn Sie eine Symbolleiste mit `CToolBarCtrl` erstellen, können Sie für diese QuickInfo Symbolleiste direkt mit folgenden Memberfunktionen implementieren: [GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md) und [SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md).  Siehe diese Features und [Behandlungs\-QuickInfo\-Benachrichtigungen](../mfc/handling-tool-tip-notifications.md) des einzelnen Mitglieds weitere Informationen dazu, wie diese QuickInfo implementieren.  
  
 Die `CToolTipCtrl`\-Klasse stellt Funktionalität des allgemeinen ToolTip\-Steuerelements Windows.  Ein einzelnes ToolTip\-Steuerelement kann Informationen für mehr als ein Tool bereitstellen.  Ein Tool ist entweder ein Fenster, z ein untergeordnetes Fenster oder Steuerelement oder ein von der Anwendung definierter rechteckiger Bereich innerhalb eines Clientbereichs des Fensters.  Die [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md)\-Klasse ist von `CToolTipCtrl` abgeleitet und stellt zusätzliche visuelle Stile und Funktionen.  
  
## Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)