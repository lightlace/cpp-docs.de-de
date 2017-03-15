---
title: 'WM_-Meldungshandler: L - M | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_WM_MENUSELECT
- ON_WM_MBUTTONDBLCLK
- ON_WM_MOUSEACTIVATE
- ON_WM_MOUSEMOVE
- ON_WM_MOVING
- ON_WM_LBUTTONUP
- ON_WM_LBUTTONDBLCLK
- ON_WM_MEASUREITEM
- ON_WM_MDIACTIVATE
- ON_WM_MOVE
- ON_WM_LBUTTONDOWN
- ON_WM_MBUTTONDOWN
- ON_WM_MENUCHAR
- ON_WM_MBUTTONUP
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_MENUSELECT
- ON_WM_MBUTTONDBLCLK
- ON_WM_MOVE
- ON_WM_MOUSEACTIVATE
- ON_WM_MBUTTONUP
- ON_WM_MOUSEMOVE
- ON_WM_MENUCHAR
- ON_WM_MBUTTONDOWN
- ON_WM_MEASUREITEM
- ON_WM_MOVING
- ON_WM_LBUTTONDOWN
- ON_WM_MDIACTIVATE
- ON_WM_LBUTTONDBLCLK
- ON_WM_LBUTTONUP
- WM_ messages
ms.assetid: 96ecaaf1-6d13-4e12-a454-535635967489
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 645e8ef051624977571830f2f1b40e54c55603f0
ms.lasthandoff: 02/24/2017

---
# <a name="wm-message-handlers-l---m"></a>WM_-Meldungshandler: L - M
Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_LBUTTONDBLCLK()|Afx_msg Void [OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk)(UINT, CPoint);|  
|ON_WM_LBUTTONDOWN()|Afx_msg Void [OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)(UINT, CPoint);|  
|ON_WM_LBUTTONUP()|Afx_msg Void [OnLButtonUp](../../mfc/reference/cwnd-class.md#onlbuttonup)(UINT, CPoint);|  
|ON_WM_MBUTTONDBLCLK()|Afx_msg Void [OnMButtonDblClk](../../mfc/reference/cwnd-class.md#onmbuttondblclk)(UINT, CPoint);|  
|ON_WM_MBUTTONDOWN()|Afx_msg Void [OnMButtonDown](../../mfc/reference/cwnd-class.md#onmbuttondown)(UINT, CPoint);|  
|ON_WM_MBUTTONUP()|Afx_msg Void [OnMButtonUp](../../mfc/reference/cwnd-class.md#onmbuttonup)(UINT, CPoint);|  
|ON_WM_MDIACTIVATE()|Afx_msg Void [OnMDIActivate](../../mfc/reference/cwnd-class.md#onmdiactivate)(BOOL CWnd * CWnd\*);|  
|ON_WM_MEASUREITEM()|Afx_msg Void [OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)(LPMEASUREITEMSTRUCT);|  
|ON_WM_MENUCHAR()|Afx_msg lang [OnMenuChar](../../mfc/reference/cwnd-class.md#onmenuchar)(UINT, UINT, CMenu *);|  
|ON_WM_MENUDRAG()|Afx_msg UINT [OnMenuDrag](../../mfc/reference/cwnd-class.md#onmenudrag)(UINT, CMenu *);|  
|ON_WM_MENUGETOBJECT()|Afx_msg UINT [OnMenuGetObject](../../mfc/reference/cwnd-class.md#onmenugetobject)(MENUGETOBJECTINFO *);|  
|ON_WM_MENURBUTTONUP()|Afx_msg Void [OnMenuRButtonUp](../../mfc/reference/cwnd-class.md#onmenurbuttonup)(UINT, CMenu *);|  
|ON_WM_MENUSELECT()|Afx_msg Void [OnMenuSelect](../../mfc/reference/cwnd-class.md#onmenuselect)(UINT, UINT, HMENU);|  
|ON_WM_MOUSEACTIVATE()|Afx_msg Int [OnMouseActivate](../../mfc/reference/cwnd-class.md#onmouseactivate)(CWnd *, "uint", "uint");|  
|ON_WM_MOUSEHOVER()|Afx_msg Void [OnMouseHover](../../mfc/reference/cwnd-class.md#onmousehover)(UINT, CPoint);|  
|ON_WM_MOUSEHWHEEL()|Afx_msg Void [OnMouseHWheel](../../mfc/reference/cwnd-class.md#onmousehwheel)(UINT, short, CPoint);|  
|ON_WM_MOUSELEAVE()|Afx_msg Void ["OnMouseLeave"](../../mfc/reference/cwnd-class.md#onmouseleave)();|  
|ON_WM_MOUSEMOVE()|Afx_msg Void [OnMouseMove](../../mfc/reference/cwnd-class.md#onmousemove)(UINT, CPoint);|  
|ON_WM_MOUSEWHEEL()|Afx_msg BOOL [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)(UINT, short, CPoint);|  
|ON_WM_MOVE()|Afx_msg Void [OnMove](../../mfc/reference/cwnd-class.md#onmove)(Int, Int);|  
|ON_WM_MOVING()|Afx_msg Void [OnMoving](../../mfc/reference/cwnd-class.md#onmoving)(UINT, LPRECT);|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)


