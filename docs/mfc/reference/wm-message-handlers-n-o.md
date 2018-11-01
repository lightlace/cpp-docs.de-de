---
title: 'WM_-Meldungshandler: N - O'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_NCHITTEST
- ON_WM_NCLBUTTONDOWN
- ON_WM_NCCALCSIZE
- ON_WM_NCLBUTTONUP
- ON_WM_NCPAINT
- ON_WM_NCMBUTTONUP
- ON_WM_NCCREATE
- ON_WM_NCACTIVATE
- ON_WM_NCMOUSEMOVE
- ON_WM_NCRBUTTONDBLCLK
- ON_WM_NCLBUTTONDBLCLK
- ON_WM_NCDESTROY
- ON_WM_NCMBUTTONDBLCLK
- ON_WM_NCRBUTTONDOWN
- ON_WM_NCRBUTTONUP
- ON_WM_NCMBUTTONDOWN
helpviewer_keywords:
- ON_WM_NCCALCSIZE [MFC]
- ON_WM_NCMBUTTONDOWN [MFC]
- ON_WM_NCRBUTTONDBLCLK [MFC]
- ON_WM_NCMBUTTONDBLCLK [MFC]
- ON_WM_NCLBUTTONDBLCLK [MFC]
- ON_WM_NCDESTROY [MFC]
- ON_WM_NCRBUTTONDOWN [MFC]
- ON_WM_NCLBUTTONDOWN [MFC]
- ON_WM_NCCREATE [MFC]
- ON_WM_NCRBUTTONUP [MFC]
- ON_WM_NCLBUTTONUP [MFC]
- ON_WM_NCPAINT [MFC]
- ON_WM_NCACTIVATE [MFC]
- ON_WM_NCHITTEST [MFC]
- ON_WM_NCMOUSEMOVE [MFC]
- ON_WM_NCMBUTTONUP [MFC]
- WM_ messages
ms.assetid: 4efd1cda-b642-4e8b-89e8-73255fa70d77
ms.openlocfilehash: 21c1ea3dfee864a4e28a0cbadfdfb73744e2d7da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619777"
---
# <a name="wm-message-handlers-n---o"></a>WM_-Meldungshandler: N - O

Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_WM_NCACTIVATE()|Afx_msg "bool" [OnNcActivate](../../mfc/reference/cwnd-class.md#onncactivate)(BOOL);|
|ON_WM_NCCALCSIZE()|die "void" Afx_msg [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)("bool", NCCALCSIZE_PARAMS weit *);|
|ON_WM_NCCREATE()|Afx_msg "bool" [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)(LPCREATESTRUCT);|
|ON_WM_NCDESTROY()|die "void" Afx_msg [OnNcDestroy](../../mfc/reference/cwnd-class.md#onncdestroy)();|
|ON_WM_NCHITTEST()|Afx_msg LRESULT [OnNcHitTest](../../mfc/reference/cwnd-class.md#onnchittest)(CPoint);|
|ON_WM_NCLBUTTONDBLCLK()|die "void" Afx_msg [OnNcLButtonDblClk](../../mfc/reference/cwnd-class.md#onnclbuttondblclk)(UINT, CPoint);|
|ON_WM_NCLBUTTONDOWN()|die "void" Afx_msg [OnNcLButtonDown](../../mfc/reference/cwnd-class.md#onnclbuttondown)(UINT, CPoint);|
|ON_WM_NCLBUTTONUP()|die "void" Afx_msg [OnNcLButtonUp](../../mfc/reference/cwnd-class.md#onnclbuttonup)(UINT, CPoint);|
|ON_WM_NCMBUTTONDBLCLK()|die "void" Afx_msg [OnNcMButtonDblClk](../../mfc/reference/cwnd-class.md#onncmbuttondblclk)(UINT, CPoint);|
|ON_WM_NCMBUTTONDOWN()|die "void" Afx_msg [OnNcMButtonDown](../../mfc/reference/cwnd-class.md#onncmbuttondown)(UINT, CPoint);|
|ON_WM_NCMBUTTONUP()|die "void" Afx_msg [OnNcMButtonUp](../../mfc/reference/cwnd-class.md#onncmbuttonup)(UINT, CPoint);|
|ON_WM_NCMOUSEHOVER()|die "void" Afx_msg [OnNcMouseHover](../../mfc/reference/cwnd-class.md#onncmousehover)(UINT, CPoint);|
|ON_WM_NCMOUSELEAVE()|die "void" Afx_msg [OnNcMouseLeave](../../mfc/reference/cwnd-class.md#onncmouseleave)();|
|ON_WM_NCMOUSEMOVE()|die "void" Afx_msg [OnNcMouseMove](../../mfc/reference/cwnd-class.md#onncmousemove)(UINT, CPoint);|
|ON_WM_NCPAINT()|die "void" Afx_msg [OnNcPaint](../../mfc/reference/cwnd-class.md#onncpaint)();|
|ON_WM_NCRBUTTONDBLCLK()|die "void" Afx_msg [OnNcRButtonDblClk](../../mfc/reference/cwnd-class.md#onncrbuttondblclk)(UINT, CPoint);|
|ON_WM_NCRBUTTONDOWN()|die "void" Afx_msg [OnNcRButtonDown](../../mfc/reference/cwnd-class.md#onncrbuttondown)(UINT, CPoint);|
|ON_WM_NCRBUTTONUP()|die "void" Afx_msg [OnNcRButtonUp](../../mfc/reference/cwnd-class.md#onncrbuttonup)(UINT, CPoint);|
|ON_WM_NCXBUTTONDBLCLK()|"void" [OnNcXButtonDblClk](../../mfc/reference/cwnd-class.md#onncxbuttondblclk)(kurz, UINT, CPoint);|
|ON_WM_NCXBUTTONDOWN()|die "void" Afx_msg [OnNcXButtonDown](../../mfc/reference/cwnd-class.md#onncxbuttondown)(kurz, UINT, CPoint);|
|ON_WM_NCXBUTTONUP()|die "void" Afx_msg [OnNcXButtonUp](../../mfc/reference/cwnd-class.md#onncxbuttonup)(kurz, UINT, CPoint);|
|ON_WM_NEXTMENU()|die "void" Afx_msg [OnNextMenu](../../mfc/reference/cwnd-class.md#onnextmenu)(UINT, LPMDINEXTMENU);|
|ON_WM_NOTIFYFORMAT()|Afx_msg UINT [OnNotifyFormat](../../mfc/reference/cwnd-class.md#onnotifyformat)(CWnd *, "uint");|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

