---
title: 'WM_-Meldungen: T - Z'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_TCARD
- ON_WM_WININICHANGE
- ON_WM_VSCROLLCLIPBOARD
- ON_WM_VSCROLL
- ON_WM_WINDOWPOSCHANGED
- ON_WM_TIMECHANGE
- ON_WM_TIMER
- ON_WM_VKEYTOITEM
- ON_WM_WINDOWPOSCHANGING
helpviewer_keywords:
- ON_WM_VSCROLLCLIPBOARD [MFC]
- ON_WM_WININICHANGE [MFC]
- ON_WM_WINDOWPOSCHANGED [MFC]
- ON_WM_TCARD [MFC]
- ON_WM_TIMECHANGE [MFC]
- ON_WM_TIMER [MFC]
- WM_ messages [MFC]
- ON_WM_WINDOWPOSCHANGING [MFC]
- ON_WM_VKEYTOITEM [MFC]
- ON_WM_VSCROLL
ms.assetid: c528bb2e-ddb5-4da6-b652-432a387408b8
ms.openlocfilehash: 7b5dbcb52ef7a61712f2c59c217a71f533799f67
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309134"
---
# <a name="wm-messages-t---z"></a>WM_-Meldungen: T - Z

Die folgenden Zuordnungseinträge entsprechen der Funktionsprototypen:

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_WM_TCARD()|die "void" Afx_msg [OnTCard](../../mfc/reference/cwnd-class.md#ontcard)(UINT, DWORD;)|
|ON_WM_TIMECHANGE()|afx_msg void [OnTimeChange](../../mfc/reference/cwnd-class.md#ontimechange)( );|
|ON_WM_TIMER()|die "void" Afx_msg [OnTimer](../../mfc/reference/cwnd-class.md#ontimer)(UINT_PTR);|
|ON_WM_UNICHAR()|afx_msg void [OnUniChar](../../mfc/reference/cwnd-class.md#onunichar)( UINT, UINT, UINT );|
|ON_WM_UNINITMENUPOPUP()|afx_msg void [OnUnInitMenuPopup](../../mfc/reference/cwnd-class.md#onuninitmenupopup)( CMenu*, UINT );|
|ON_WM_USERCHANGED()|die "void" Afx_msg [OnUserChanged](../../mfc/reference/cwnd-class.md#onuserchanged)();|
|ON_WM_VKEYTOITEM()|afx_msg int [OnVKeyToItem](../../mfc/reference/cwnd-class.md#onvkeytoitem)( UINT, CWnd*, UINT );|
|ON_WM_VSCROLL()|die "void" Afx_msg [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)("uint", "uint", CWnd *);|
|ON_WM_VSCROLLCLIPBOARD()|die "void" Afx_msg [OnVScrollClipboard](../../mfc/reference/cwnd-class.md#onvscrollclipboard)(CWnd *, "uint", "uint");|
|ON_WM_WINDOWPOSCHANGED()|die "void" Afx_msg [OnWindowPosChanged](../../mfc/reference/cwnd-class.md#onwindowposchanged)(WINDOWPOS *);|
|ON_WM_WINDOWPOSCHANGING()|die "void" Afx_msg [OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)(WINDOWPOS *);|
|ON_WM_WININICHANGE()|afx_msg void [OnWinIniChange](../../mfc/reference/cwnd-class.md#onwininichange)( LPSTR );|
|ON_WM_WTSSESSION_CHANGE()|die "void" Afx_msg [OnSessionChange](../../mfc/reference/cwnd-class.md#onsessionchange)("uint", "uint");|
|ON_WM_XBUTTONDBLCLK()|afx_msg void [OnXButtonDblClk](../../mfc/reference/cwnd-class.md#onxbuttondblclk)( UINT, UINT, CPoint );|
|ON_WM_XBUTTONDOWN()|die "void" Afx_msg [OnXButtonDown](../../mfc/reference/cwnd-class.md#onxbuttondown)("uint", "uint", CPoint);|
|ON_WM_XBUTTONUP()|die "void" Afx_msg [OnXButtonUp](../../mfc/reference/cwnd-class.md#onxbuttonup)("uint", "uint", CPoint);|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)
