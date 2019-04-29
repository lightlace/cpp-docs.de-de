---
title: 'WM_-Meldungshandler: A - C'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_CREATE
- ON_WM_COMPACTING
- ON_WM_CHARTOITEM
- ON_WM_ASKCBFORMATNAME
- ON_WM_CTLCOLOR
- ON_WM_COMPAREITEM
- ON_WM_CHILDACTIVATE
- ON_WM_CONTEXTMENU
- ON_WM_ACTIVATE
- ON_WM_CANCELMODE
- ON_WM_CLOSE
- ON_WM_CAPTURECHANGED
- ON_WM_ACTIVATEAPP
- ON_WM_CHAR
- ON_WM_CHANGECBCHAIN
helpviewer_keywords:
- ON_WM_COMPACTING [MFC]
- ON_WM_COMPAREITEM [MFC]
- ON_WM_CLOSE [MFC]
- ON_WM_CTLCOLOR [MFC]
- ON_WM_CHAR [MFC]
- ON_WM_CAPTURECHANGED [MFC]
- ON_WM_CHARTOITEM [MFC]
- ON_WM_CREATE [MFC]
- ON_WM_ACTIVATE [MFC]
- ON_WM_CONTEXTMENU [MFC]
- ON_WM_CANCELMODE [MFC]
- ON_WM_ASKCBFORMATNAME [MFC]
- ON_WM_CHILDACTIVATE [MFC]
- WM_ messages [MFC]
- ON_WM_ACTIVATEAPP [MFC]
- ON_WM_CHANGECBCHAIN
ms.assetid: 4e315896-d646-4b87-b0ab-41a4a753b045
ms.openlocfilehash: 08221e7569a8b4c4f4e8decba410bd1fe40f04d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309394"
---
# <a name="wm-message-handlers-a---c"></a>WM_-Meldungshandler: A - C

Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_WM_ACTIVATE()|die "void" Afx_msg [OnActivate](../../mfc/reference/cwnd-class.md#onactivate)(UINT, CWnd\*, "bool");|
|ON_WM_ACTIVATEAPP()|die "void" Afx_msg [OnActivateApp](../../mfc/reference/cwnd-class.md#onactivateapp)("bool", DWORD;)|
|ON_WM_APPCOMMAND()|die "void" Afx_msg [OnAppCommand](../../mfc/reference/cwnd-class.md#onappcommand)(CWnd\*, "uint", "uint", "uint");|
|ON_WM_ASKCBFORMATNAME()|die "void" Afx_msg [OnAskCbFormatName](../../mfc/reference/cwnd-class.md#onaskcbformatname)(UINT, LPSTR);|
|ON_WM_CANCELMODE()|die "void" Afx_msg [OnCancelMode](../../mfc/reference/cwnd-class.md#oncancelmode)();|
|ON_WM_CAPTURECHANGED()|die "void" Afx_msg [OnCaptureChanged](../../mfc/reference/cwnd-class.md#oncapturechanged)(CWnd\*);|
|ON_WM_CHANGECBCHAIN()|die "void" Afx_msg [OnChangeCbChain](../../mfc/reference/cwnd-class.md#onchangecbchain)(HWND, HWND);|
|ON_WM_CHAR()|die "void" Afx_msg [OnChar](../../mfc/reference/cwnd-class.md#onchar)("uint", "uint", "uint");|
|ON_WM_CHARTOITEM()|Afx_msg Int [OnCharToItem](../../mfc/reference/cwnd-class.md#onchartoitem)(UINT, CWnd\*, "uint");|
|ON_WM_CHILDACTIVATE()|die "void" Afx_msg [OnChildActivate](../../mfc/reference/cwnd-class.md#onchildactivate)();|
|ON_WM_CLIPBOARDUPDATE()|die "void" Afx_msg [OnClipboardUpdate](../../mfc/reference/cwnd-class.md#onclipboardupdate)();|
|ON_WM_CLOSE()|die "void" Afx_msg [OnClose](../../mfc/reference/cwnd-class.md#onclose)();|
|ON_WM_COMPACTING()|die "void" Afx_msg [OnCompacting](../../mfc/reference/cwnd-class.md#oncompacting)(UINT);|
|ON_WM_COMPAREITEM()|afx_msg int [OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)(LPCOMPAREITEMSTRUCT);|
|ON_WM_CONTEXTMENU()|die "void" Afx_msg [OnContextMenu](../../mfc/reference/cwnd-class.md#oncontextmenu)(CWnd\*, CPoint);|
|ON_WM_COPYDATA()|afx_msg BOOL [OnCopyData](../../mfc/reference/cwnd-class.md#oncopydata)(CWnd\* pWnd, COPYDATASTRUCT\* pCopyDataStruct);|
|ON_WM_CREATE()|afx_msg int [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)(LPCREATESTRUCT);|
|ON_WM_CTLCOLOR()|Afx_msg HBRUSH [OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor)(CDC\*, CWnd\*, "uint");|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)
