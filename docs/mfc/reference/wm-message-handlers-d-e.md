---
title: 'WM_-Meldungshandler: D - E'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_ERASEBKGND
- ON_WM_DEVICECHANGE
- ON_WM_ENTERIDLE
- ON_WM_DESTROYCLIPBOARD
- ON_WM_DESTROY
- ON_WM_DEADCHAR
- ON_WM_DELETEITEM
- ON_WM_DROPFILES
- ON_WM_DEVMODECHANGE
- ON_WM_ENDSESSION
- ON_WM_ENABLE
- ON_WM_DRAWITEM
- ON_WM_DRAWCLIPBOARD
helpviewer_keywords:
- ON_WM_ENTERIDLE [MFC]
- ON_WM_DESTROYCLIPBOARD [MFC]
- ON_WM_DEADCHAR [MFC]
- ON_WM_DEVMODECHANGE [MFC]
- ON_WM_ERASEBKGND [MFC]
- ON_WM_DESTROY [MFC]
- ON_WM_DRAWCLIPBOARD [MFC]
- ON_WM_ENDSESSION [MFC]
- ON_WM_DRAWITEM [MFC]
- ON_WM_ENABLE [MFC]
- ON_WM_DROPFILES [MFC]
- ON_WM_DELETEITEM [MFC]
- ON_WM_DEVICECHANGE [MFC]
- WM_ messages [MFC]
ms.assetid: 56fb89c8-68a8-4adf-883e-a9f63bf677e9
ms.openlocfilehash: 3ae9ff828f342bc4270c3701ced3e670988c7d54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309290"
---
# <a name="wm-message-handlers-d---e"></a>WM_-Meldungshandler: D - E

Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_WM_DEADCHAR()|die "void" Afx_msg [OnDeadChar](../../mfc/reference/cwnd-class.md#ondeadchar)("uint", "uint", "uint");|
|ON_WM_DELETEITEM()|afx_msg void [OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)(LPDELETEITEMSTRUCT);|
|ON_WM_DESTROY()|die "void" Afx_msg [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)();|
|ON_WM_DESTROYCLIPBOARD()|die "void" Afx_msg [OnDestroyClipboard](../../mfc/reference/cwnd-class.md#ondestroyclipboard)();|
|ON_WM_DEVICECHANGE()|die "void" Afx_msg [OnDeviceChange](../../mfc/reference/cwnd-class.md#ondevicechange)(UINT, DWORD;)|
|ON_WM_DEVMODECHANGE()|die "void" Afx_msg [OnDevModeChange](../../mfc/reference/cwnd-class.md#ondevmodechange)(LPSTR);|
|ON_WM_DRAWCLIPBOARD()|die "void" Afx_msg [OnDrawClipboard](../../mfc/reference/cwnd-class.md#ondrawclipboard)();|
|ON_WM_DRAWITEM()|die "void" Afx_msg [OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)(LPDRAWITEMSTRUCT);|
|ON_WM_DROPFILES()|die "void" Afx_msg [OnDropFiles](../../mfc/reference/cwnd-class.md#ondropfiles)(HDROP);|
|ON_WM_DWMCOLORIZATIONCOLORCHANGED()|die "void" Afx_msg [OnColorizationColorChanged](../../mfc/reference/cwnd-class.md#oncolorizationcolorchanged)(DWORD-, "bool");|
|ON_WM_DWMCOMPOSITIONCHANGED()|die "void" Afx_msg [OnCompositionChanged](../../mfc/reference/cwnd-class.md#oncompositionchanged)();|
|ON_WM_DWMNCRENDERINGCHANGED()|die "void" Afx_msg [OnNcRenderingChanged](../../mfc/reference/cwnd-class.md#onncrenderingchanged)(BOOL);|
|ON_WM_DWMWINDOWMAXIMIZEDCHANGE()|die "void" Afx_msg [OnWindowMaximizedChanged](../../mfc/reference/cwnd-class.md#onwindowmaximizedchanged)(BOOL);|
|ON_WM_ENABLE()|die "void" Afx_msg [OnEnable](../../mfc/reference/cwnd-class.md#onenable)(BOOL);|
|ON_WM_ENDSESSION()|die "void" Afx_msg [OnEndSession](../../mfc/reference/cwnd-class.md#onendsession)(BOOL);|
|ON_WM_ENTERIDLE()|die "void" Afx_msg [OnEnterIdle](../../mfc/reference/cwnd-class.md#onenteridle)(UINT, CWnd *);|
|ON_WM_ENTERSIZEMOVE()|die "void" Afx_msg [OnEnterSizeMove](../../mfc/reference/cwnd-class.md#onentersizemove)();|
|ON_WM_ERASEBKGND()|afx_msg BOOL [OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd)(CDC*);|
|ON_WM_EXITSIZEMOVE()|die "void" Afx_msg [OnExitSizeMove](../../mfc/reference/cwnd-class.md#onexitsizemove)();|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)
