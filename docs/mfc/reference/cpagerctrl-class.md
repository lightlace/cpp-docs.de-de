---
title: "CPagerCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPagerCtrl class"
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CPagerCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CPagerCtrl`\-Klasse umschließt das Windows\-Pager\-Steuerelement ein, das in Ansicht ein Containerelement Fenster wechseln kann, die nicht dem Fenster passt.  
  
## Syntax  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPagerCtrl::CPagerCtrl](../Topic/CPagerCtrl::CPagerCtrl.md)|Erstellt ein `CPagerCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPagerCtrl::Create](../Topic/CPagerCtrl::Create.md)|Erstellt ein Pager\-Steuerelement mit angegebenen Formaten und weist dieses dem aktuellen `CPagerCtrl`\-Objekt.|  
|[CPagerCtrl::CreateEx](../Topic/CPagerCtrl::CreateEx.md)|Erstellt ein Pager\-Steuerelement mit angegebenen erweiterten Formaten und weist dieses dem aktuellen `CPagerCtrl`\-Objekt.|  
|[CPagerCtrl::ForwardMouse](../Topic/CPagerCtrl::ForwardMouse.md)|Aktiviert oder deaktiviert das Weiterleiten von [WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) Meldungen in das Fenster, das im aktuellen Pager\-Steuerelement enthalten ist.|  
|[CPagerCtrl::GetBkColor](../Topic/CPagerCtrl::GetBkColor.md)|Ruft die Hintergrundfarbe des aktuellen Pager\-Steuerelements ab.|  
|[CPagerCtrl::GetBorder](../Topic/CPagerCtrl::GetBorder.md)|Ruft die Rahmengröße des aktuellen Pager\-Steuerelements ab.|  
|[CPagerCtrl::GetButtonSize](../Topic/CPagerCtrl::GetButtonSize.md)|Ruft die Schaltflächengröße des aktuellen Pager\-Steuerelements ab.|  
|[CPagerCtrl::GetButtonState](../Topic/CPagerCtrl::GetButtonState.md)|Ruft den Zustand der angegebenen Schaltfläche im aktuellen Pager\-Steuerelement ab.|  
|[CPagerCtrl::GetDropTarget](../Topic/CPagerCtrl::GetDropTarget.md)|Ruft die [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)\-Schnittstelle für das aktuelle Pager\-Steuerelement ab.|  
|[CPagerCtrl::GetScrollPos](../Topic/CPagerCtrl::GetScrollPos.md)|Ruft die Bildlaufposition des aktuellen Pager\-Steuerelements ab.|  
|[CPagerCtrl::IsButtonDepressed](../Topic/CPagerCtrl::IsButtonDepressed.md)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager\-Steuerelements in `pressed` Zustand befindet.|  
|[CPagerCtrl::IsButtonGrayed](../Topic/CPagerCtrl::IsButtonGrayed.md)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager\-Steuerelements in `grayed` Zustand befindet.|  
|[CPagerCtrl::IsButtonHot](../Topic/CPagerCtrl::IsButtonHot.md)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager\-Steuerelements in `hot` Zustand befindet.|  
|[CPagerCtrl::IsButtonInvisible](../Topic/CPagerCtrl::IsButtonInvisible.md)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager\-Steuerelements in `invisible` Zustand befindet.|  
|[CPagerCtrl::IsButtonNormal](../Topic/CPagerCtrl::IsButtonNormal.md)|Gibt an, ob die angegebene Schaltfläche des aktuellen Pager\-Steuerelements in `normal` Zustand befindet.|  
|[CPagerCtrl::RecalcSize](../Topic/CPagerCtrl::RecalcSize.md)|Veranlasst das aktuelle Pager\-Steuerelement, die Größe des übergeordneten Fensters neu zu berechnen.|  
|[CPagerCtrl::SetBkColor](../Topic/CPagerCtrl::SetBkColor.md)|Legt die Hintergrundfarbe des aktuellen Pager\-Steuerelements fest.|  
|[CPagerCtrl::SetBorder](../Topic/CPagerCtrl::SetBorder.md)|Legt die Rahmengröße des aktuellen Pager\-Steuerelements fest.|  
|[CPagerCtrl::SetButtonSize](../Topic/CPagerCtrl::SetButtonSize.md)|Legt die Schaltflächengröße des aktuellen Pager\-Steuerelements fest.|  
|[CPagerCtrl::SetChild](../Topic/CPagerCtrl::SetChild.md)|Legt das enthaltende Fenster für das aktuelle Pager\-Steuerelement fest.|  
|[CPagerCtrl::SetScrollPos](../Topic/CPagerCtrl::SetScrollPos.md)|Legt die Bildlaufposition des aktuellen Pager\-Steuerelements fest.|  
  
## Hinweise  
 Ein Pager\-Steuerelement ist ein Fenster, das ein anderes Fenster enthält, das linear und größer als dem Fenster ist und es ermöglicht, das enthaltende Fenster in einblenden.  Das Pager\-Steuerelement werden zwei Bildlaufschaltflächen an, die automatisch ausgeblendet werden, wenn das enthaltende Fenster zu seinem Wertebereich weitesten Bildlauf ausgeführt wird, und andernfalls erneut angezeigt werden.  Sie können ein Pager\-Steuerelement erstellen, das horizontal oder vertikal durch.  
  
 Wenn die Anwendung beispielsweise eine Symbolleiste verfügt, die nicht weit genug, alle Elemente anzuzeigen, können Sie die Symbolleiste zu einem Pager\-Steuerelement zuweisen und Benutzer sind, Symbolleiste zu dem linken oder rechten liegen, um auf alle Elemente zuzugreifen.  Microsoft Internet Explorer 4,0 \(commctrl.dll\-Version 4.71\) stellt das Pager\-Steuerelement vor.  
  
 Die `CPagerCtrl`\-Klasse wird von [CWnd](../../mfc/reference/cwnd-class.md)\-Klasse abgeleitet.  Weitere Informationen und eine Abbildung eines Pager\-Steuerelements, finden Sie unter [Pager\-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760855).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPagerCtrl`  
  
## Anforderungen  
 **Header:** afxcmn.h  
  
## Siehe auch  
 [CPagerCtrl Class](../../mfc/reference/cpagerctrl-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Pager\-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb760855)