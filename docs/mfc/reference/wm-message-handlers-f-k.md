---
title: 'WM_-Meldungshandler: F - K | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_WM_FONTCHANGE
- ON_WM_ICONERASEBKGND
- ON_WM_KEYDOWN
- ON_WM_GETMINMAXINFO
- ON_WM_KEYUP
- ON_WM_HSCROLL
- ON_WM_KILLFOCUS
- ON_WM_HSCROLLCLIPBOARD
- ON_WM_GETDLGCODE
- ON_WM_HELPINFO
- ON_WM_INITMENUPOPUP
- ON_WM_INITMENU
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_HELPINFO [MFC]
- ON_WM_KILLFOCUS [MFC]
- ON_WM_GETMINMAXINFO [MFC]
- ON_WM_KEYUP [MFC]
- ON_WM_HSCROLL [MFC]
- ON_WM_INITMENUPOPUP [MFC]
- ON_WM_FONTCHANGE [MFC]
- ON_WM_ICONERASEBKGND [MFC]
- ON_WM_GETDLGCODE [MFC]
- ON_WM_HSCROLLCLIPBOARD [MFC]
- ON_WM_INITMENU [MFC]
- WM_ messages [MFC]
- ON_WM_KEYDOWN [MFC]
ms.assetid: 0e7de191-1499-499f-859c-62742797808e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d33b91cf68055c47afb25ca1b2f68b245c2aed3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414562"
---
# <a name="wm-message-handlers-f---k"></a>WM_-Meldungshandler: F - K

Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_WM_FONTCHANGE()|die "void" Afx_msg [OnFontChange](../../mfc/reference/cwnd-class.md#onfontchange)();|
|ON_WM_GETDLGCODE()|Afx_msg UINT [OnGetDlgCode](../../mfc/reference/cwnd-class.md#ongetdlgcode)();|
|ON_WM_GETMINMAXINFO()|die "void" Afx_msg [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)(LPPOINT);|
|ON_WM_HELPINFO()|Afx_msg "bool" [OnHelpInfo](../../mfc/reference/cwnd-class.md#onhelpinfo)(HELPINFO *);|
|ON_WM_HOTKEY()|die "void" Afx_msg [OnHotKey](../../mfc/reference/cwnd-class.md#onhotkey)("uint", "uint", "uint");|
|ON_WM_HSCROLL()|die "void" Afx_msg [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)("uint", "uint", CWnd *);|
|ON_WM_HSCROLLCLIPBOARD()|die "void" Afx_msg [OnHScrollClipboard](../../mfc/reference/cwnd-class.md#onhscrollclipboard)(CWnd *, "uint", "uint");|
|ON_WM_ICONERASEBKGND()|die "void" Afx_msg [OnIconEraseBkgnd](../../mfc/reference/cwnd-class.md#oniconerasebkgnd)(CDC *);|
|ON_WM_INITMENU()|die "void" Afx_msg [OnInitMenu](../../mfc/reference/cwnd-class.md#oninitmenu)(CMenu *);|
|ON_WM_INITMENUPOPUP()|die "void" Afx_msg [OnInitMenuPopup](../../mfc/reference/cwnd-class.md#oninitmenupopup)(CMenu *, "uint", "bool");|
|ON_WM_INPUT()|die "void" Afx_msg [OnRawInput](../../mfc/reference/cwnd-class.md#onrawinput)(UINT, HRAWINPUT);|
|ON_WM_INPUT_DEVICE_CHANGE()|die "void" Afx_msg [OnInputDeviceChange](../../mfc/reference/cwnd-class.md#oninputdevicechange)(kurz ohne Vorzeichen);|
|ON_WM_INPUTLANGCHANGE()|die "void" Afx_msg [OnInputLangChange](../../mfc/reference/cwnd-class.md#oninputlangchange)(BYTE, "uint");|
|ON_WM_INPUTLANGCHANGEREQUEST()|die "void" Afx_msg [OnInputLangChangeRequest](../../mfc/reference/cwnd-class.md#oninputlangchangerequest)(UINT, HKL);|
|ON_WM_KEYDOWN()|die "void" Afx_msg [OnKeyDown](../../mfc/reference/cwnd-class.md#onkeydown)("uint", "uint", "uint");|
|ON_WM_KEYUP()|die "void" Afx_msg [OnKeyUp](../../mfc/reference/cwnd-class.md#onkeyup)("uint", "uint", "uint");|
|ON_WM_KILLFOCUS()|die "void" Afx_msg [OnKillFocus](../../mfc/reference/cwnd-class.md#onkillfocus)(CWnd *);|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

