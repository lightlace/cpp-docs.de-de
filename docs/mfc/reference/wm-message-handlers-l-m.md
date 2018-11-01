---
title: 'WM_-Meldungshandler: L - M | Microsoft-Dokumentation'
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
ms.openlocfilehash: afb716b6ee334ebfc3c974ae4caf715d45a2dcc0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426743"
---
# <a name="wm-message-handlers-l---m"></a>WM_-Meldungshandler: L - M

Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_WM_LBUTTONDBLCLK()|die "void" Afx_msg [OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk)(UINT, CPoint);|
|ON_WM_LBUTTONDOWN()|die "void" Afx_msg [OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)(UINT, CPoint);|
|ON_WM_LBUTTONUP()|die "void" Afx_msg [OnLButtonUp](../../mfc/reference/cwnd-class.md#onlbuttonup)(UINT, CPoint);|
|ON_WM_MBUTTONDBLCLK()|die "void" Afx_msg [OnMButtonDblClk](../../mfc/reference/cwnd-class.md#onmbuttondblclk)(UINT, CPoint);|
|ON_WM_MBUTTONDOWN()|die "void" Afx_msg [OnMButtonDown](../../mfc/reference/cwnd-class.md#onmbuttondown)(UINT, CPoint);|
|ON_WM_MBUTTONUP()|die "void" Afx_msg [OnMButtonUp](../../mfc/reference/cwnd-class.md#onmbuttonup)(UINT, CPoint);|
|ON_WM_MDIACTIVATE()|die "void" Afx_msg [OnMDIActivate](../../mfc/reference/cwnd-class.md#onmdiactivate)("bool", CWnd\*, CWnd\*);|
|ON_WM_MEASUREITEM()|die "void" Afx_msg [OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)(LPMEASUREITEMSTRUCT);|
|ON_WM_MENUCHAR()|Afx_msg lang [OnMenuChar](../../mfc/reference/cwnd-class.md#onmenuchar)("uint", "uint", CMenu\*);|
|ON_WM_MENUDRAG()|Afx_msg UINT [OnMenuDrag](../../mfc/reference/cwnd-class.md#onmenudrag)(UINT, CMenu\*);|
|ON_WM_MENUGETOBJECT()|Afx_msg UINT [OnMenuGetObject](../../mfc/reference/cwnd-class.md#onmenugetobject)(MENUGETOBJECTINFO\*);|
|ON_WM_MENURBUTTONUP()|die "void" Afx_msg [OnMenuRButtonUp](../../mfc/reference/cwnd-class.md#onmenurbuttonup)(UINT, CMenu\*);|
|ON_WM_MENUSELECT()|die "void" Afx_msg [OnMenuSelect](../../mfc/reference/cwnd-class.md#onmenuselect)("uint", "uint", HMENU);|
|ON_WM_MOUSEACTIVATE()|Afx_msg Int [OnMouseActivate](../../mfc/reference/cwnd-class.md#onmouseactivate)(CWnd\*, "uint", "uint");|
|ON_WM_MOUSEHOVER()|die "void" Afx_msg [OnMouseHover](../../mfc/reference/cwnd-class.md#onmousehover)(UINT, CPoint);|
|ON_WM_MOUSEHWHEEL()|die "void" Afx_msg [OnMouseHWheel](../../mfc/reference/cwnd-class.md#onmousehwheel)(UINT, short, CPoint);|
|ON_WM_MOUSELEAVE()|die "void" Afx_msg [OnMouseLeave](../../mfc/reference/cwnd-class.md#onmouseleave)();|
|ON_WM_MOUSEMOVE()|die "void" Afx_msg [OnMouseMove](../../mfc/reference/cwnd-class.md#onmousemove)(UINT, CPoint);|
|ON_WM_MOUSEWHEEL()|Afx_msg "bool" [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)(UINT, short, CPoint);|
|ON_WM_MOVE()|die "void" Afx_msg [OnMove](../../mfc/reference/cwnd-class.md#onmove)(Int, Int);|
|ON_WM_MOVING()|die "void" Afx_msg [OnMoving](../../mfc/reference/cwnd-class.md#onmoving)(UINT, LPRECT);|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

