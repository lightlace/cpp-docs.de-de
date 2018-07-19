---
title: 'WM_-Meldungshandler: L - M | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
- ON_WM_MENUSELECT [MFC]
- ON_WM_MBUTTONDBLCLK [MFC]
- ON_WM_MOVE [MFC]
- ON_WM_MOUSEACTIVATE [MFC]
- ON_WM_MBUTTONUP [MFC]
- ON_WM_MOUSEMOVE [MFC]
- ON_WM_MENUCHAR [MFC]
- ON_WM_MBUTTONDOWN [MFC]
- ON_WM_MEASUREITEM [MFC]
- ON_WM_MOVING [MFC]
- ON_WM_LBUTTONDOWN [MFC]
- ON_WM_MDIACTIVATE [MFC]
- ON_WM_LBUTTONDBLCLK [MFC]
- ON_WM_LBUTTONUP [MFC]
- WM_ messages
ms.assetid: 96ecaaf1-6d13-4e12-a454-535635967489
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2697ed09043cb14e57b5f62aad9b9a660446e84a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379599"
---
# <a name="wm-message-handlers-l---m"></a>WM_-Meldungshandler: L - M
Die folgenden Zuordnungseinträge auf der linken Seite entsprechen auf der rechten Seite der Funktionsprototypen:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_LBUTTONDBLCLK()|Afx_msg "void" [OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk)("uint", CPoint);|  
|ON_WM_LBUTTONDOWN()|Afx_msg "void" [OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)("uint", CPoint);|  
|ON_WM_LBUTTONUP()|Afx_msg "void" [OnLButtonUp](../../mfc/reference/cwnd-class.md#onlbuttonup)("uint", CPoint);|  
|ON_WM_MBUTTONDBLCLK()|Afx_msg "void" [OnMButtonDblClk](../../mfc/reference/cwnd-class.md#onmbuttondblclk)("uint", CPoint);|  
|ON_WM_MBUTTONDOWN()|Afx_msg "void" [OnMButtonDown](../../mfc/reference/cwnd-class.md#onmbuttondown)("uint", CPoint);|  
|ON_WM_MBUTTONUP()|Afx_msg "void" [OnMButtonUp](../../mfc/reference/cwnd-class.md#onmbuttonup)("uint", CPoint);|  
|ON_WM_MDIACTIVATE()|Afx_msg "void" [OnMDIActivate](../../mfc/reference/cwnd-class.md#onmdiactivate)(BOOL CWnd * CWnd\*);|  
|ON_WM_MEASUREITEM()|Afx_msg "void" [OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)(LPMEASUREITEMSTRUCT);|  
|ON_WM_MENUCHAR()|Afx_msg lang [OnMenuChar](../../mfc/reference/cwnd-class.md#onmenuchar)("uint", "uint", CMenu *);|  
|ON_WM_MENUDRAG()|Afx_msg "uint" [OnMenuDrag](../../mfc/reference/cwnd-class.md#onmenudrag)("uint", CMenu *);|  
|ON_WM_MENUGETOBJECT()|Afx_msg "uint" [OnMenuGetObject](../../mfc/reference/cwnd-class.md#onmenugetobject)(MENUGETOBJECTINFO *);|  
|ON_WM_MENURBUTTONUP()|Afx_msg "void" [OnMenuRButtonUp](../../mfc/reference/cwnd-class.md#onmenurbuttonup)("uint", CMenu *);|  
|ON_WM_MENUSELECT()|Afx_msg "void" [OnMenuSelect](../../mfc/reference/cwnd-class.md#onmenuselect)("uint", "uint", HMENU)|  
|ON_WM_MOUSEACTIVATE()|Afx_msg Int [OnMouseActivate](../../mfc/reference/cwnd-class.md#onmouseactivate)(CWnd *, "uint", "uint");|  
|ON_WM_MOUSEHOVER()|Afx_msg "void" [OnMouseHover](../../mfc/reference/cwnd-class.md#onmousehover)("uint", CPoint);|  
|ON_WM_MOUSEHWHEEL()|Afx_msg "void" [OnMouseHWheel](../../mfc/reference/cwnd-class.md#onmousehwheel)("uint", short, CPoint);|  
|ON_WM_MOUSELEAVE()|Afx_msg "void" ["OnMouseLeave"](../../mfc/reference/cwnd-class.md#onmouseleave)();|  
|ON_WM_MOUSEMOVE()|Afx_msg "void" [OnMouseMove](../../mfc/reference/cwnd-class.md#onmousemove)("uint", CPoint);|  
|ON_WM_MOUSEWHEEL()|Afx_msg BOOL [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)("uint", short, CPoint);|  
|ON_WM_MOVE()|Afx_msg "void" [OnMove](../../mfc/reference/cwnd-class.md#onmove)(Int, Int);|  
|ON_WM_MOVING()|Afx_msg "void" [OnMoving](../../mfc/reference/cwnd-class.md#onmoving)("uint", LPRECT);|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

