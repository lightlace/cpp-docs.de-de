---
title: "WM_-Meldungen: T - Z"
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
  - "ON_WM_TCARD"
  - "ON_WM_WININICHANGE"
  - "ON_WM_VSCROLLCLIPBOARD"
  - "ON_WM_VSCROLL"
  - "ON_WM_WINDOWPOSCHANGED"
  - "ON_WM_TIMECHANGE"
  - "ON_WM_TIMER"
  - "ON_WM_VKEYTOITEM"
  - "ON_WM_WINDOWPOSCHANGING"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_TCARD"
  - "ON_WM_TIMECHANGE"
  - "ON_WM_TIMER"
  - "ON_WM_VKEYTOITEM"
  - "ON_WM_VSCROLL"
  - "ON_WM_VSCROLLCLIPBOARD"
  - "ON_WM_WINDOWPOSCHANGED"
  - "ON_WM_WINDOWPOSCHANGING"
  - "ON_WM_WININICHANGE"
  - "WM_-Meldungen"
ms.assetid: c528bb2e-ddb5-4da6-b652-432a387408b8
caps.latest.revision: 16
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# WM_-Meldungen: T - Z
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Einträge die folgende Zuordnung entsprechen den Funktionsprototypen:  
  
|Zuordnungseintrag|Funktionsprototyp|  
|-----------------------|-----------------------|  
|ON\_WM\_TCARD\(\)|afx\_msg void [OnTCard](../Topic/CWnd::OnTCard.md)\(UINT, DWORD\);|  
|ON\_WM\_TIMECHANGE\(\)|afx\_msg void [OnTimeChange](../Topic/CWnd::OnTimeChange.md)\(\);|  
|ON\_WM\_TIMER\(\)|afx\_msg void [OnTimer](../Topic/CWnd::OnTimer.md)\(UINT\_PTR\);|  
|ON\_WM\_UNICHAR\(\)|afx\_msg void [OnUniChar](../Topic/CWnd::OnUniChar.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_UNINITMENUPOPUP\(\)|afx\_msg void [OnUnInitMenuPopup](../Topic/CWnd::OnUnInitMenuPopup.md)\(CMenu\*, UINT\);|  
|ON\_WM\_USERCHANGED\(\)|afx\_msg void [OnUserChanged](../Topic/CWnd::OnUserChanged.md)\(\);|  
|ON\_WM\_VKEYTOITEM\(\)|afx\_msg int [OnVKeyToItem](../Topic/CWnd::OnVKeyToItem.md)\(UINT, CWnd\*, UINT\);|  
|ON\_WM\_VSCROLL\(\)|afx\_msg void [OnVScroll](../Topic/CWnd::OnVScroll.md)\(UINT, UINT, CWnd\*\);|  
|ON\_WM\_VSCROLLCLIPBOARD\(\)|afx\_msg void [OnVScrollClipboard](../Topic/CWnd::OnVScrollClipboard.md)\(CWnd\*, UINT, UINT\);|  
|ON\_WM\_WINDOWPOSCHANGED\(\)|afx\_msg void [OnWindowPosChanged](../Topic/CWnd::OnWindowPosChanged.md)\(WINDOWPOS\*\);|  
|ON\_WM\_WINDOWPOSCHANGING\(\)|afx\_msg void [OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)\(WINDOWPOS\*\);|  
|ON\_WM\_WININICHANGE\(\)|afx\_msg void [OnWinIniChange](../Topic/CWnd::OnWinIniChange.md)\(LPSTR\);|  
|ON\_WM\_WTSSESSION\_CHANGE\(\)|afx\_msg void [OnSessionChange](../Topic/CWnd::OnSessionChange.md)\(UINT, UINT\);|  
|ON\_WM\_XBUTTONDBLCLK\(\)|afx\_msg void [OnXButtonDblClk](../Topic/CWnd::OnXButtonDblClk.md)\(UINT, UINT, CPoint\);|  
|ON\_WM\_XBUTTONDOWN\(\)|afx\_msg void [OnXButtonDown](../Topic/CWnd::OnXButtonDown.md)\(UINT, UINT, CPoint\);|  
|ON\_WM\_XBUTTONUP\(\)|afx\_msg void [OnXButtonUp](../Topic/CWnd::OnXButtonUp.md)\(UINT, UINT, CPoint\);|  
  
## Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM\_\-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)