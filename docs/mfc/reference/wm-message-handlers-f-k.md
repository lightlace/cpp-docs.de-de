---
title: 'WM_-Meldungshandler: F - K | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 974c8bf9f1100497752b4aa4b5f796440c75d08f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wm-message-handlers-f---k"></a>WM_-Meldungshandler: F - K
Die folgenden Zuordnungseinträge auf der linken Seite entsprechen auf der rechten Seite der Funktionsprototypen:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_FONTCHANGE()|Afx_msg "void" [OnFontChange](../../mfc/reference/cwnd-class.md#onfontchange)(;)|  
|ON_WM_GETDLGCODE()|Afx_msg "uint" [OnGetDlgCode](../../mfc/reference/cwnd-class.md#ongetdlgcode)(;)|  
|ON_WM_GETMINMAXINFO()|Afx_msg "void" [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)(LPPOINT);|  
|ON_WM_HELPINFO()|Afx_msg BOOL [OnHelpInfo](../../mfc/reference/cwnd-class.md#onhelpinfo)(HELPINFO *);|  
|ON_WM_HOTKEY()|Afx_msg "void" [OnHotKey](../../mfc/reference/cwnd-class.md#onhotkey)("uint", "uint", "uint");|  
|ON_WM_HSCROLL()|Afx_msg "void" [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)("uint", "uint", CWnd *);|  
|ON_WM_HSCROLLCLIPBOARD()|Afx_msg "void" [OnHScrollClipboard](../../mfc/reference/cwnd-class.md#onhscrollclipboard)(CWnd *, "uint", "uint");|  
|ON_WM_ICONERASEBKGND()|Afx_msg "void" [OnIconEraseBkgnd](../../mfc/reference/cwnd-class.md#oniconerasebkgnd)(CDC *);|  
|ON_WM_INITMENU()|Afx_msg "void" [OnInitMenu](../../mfc/reference/cwnd-class.md#oninitmenu)(CMenu *);|  
|ON_WM_INITMENUPOPUP()|Afx_msg "void" [OnInitMenuPopup](../../mfc/reference/cwnd-class.md#oninitmenupopup)(CMenu *, "uint", BOOL);|  
|ON_WM_INPUT()|Afx_msg "void" [OnRawInput](../../mfc/reference/cwnd-class.md#onrawinput)("uint", HRAWINPUT);|  
|ON_WM_INPUT_DEVICE_CHANGE()|Afx_msg "void" [OnInputDeviceChange](../../mfc/reference/cwnd-class.md#oninputdevicechange)(kurz ohne Vorzeichen);|  
|ON_WM_INPUTLANGCHANGE()|Afx_msg "void" [OnInputLangChange](../../mfc/reference/cwnd-class.md#oninputlangchange)(BYTE, "uint");|  
|ON_WM_INPUTLANGCHANGEREQUEST()|Afx_msg "void" [OnInputLangChangeRequest](../../mfc/reference/cwnd-class.md#oninputlangchangerequest)("uint", HKL);|  
|ON_WM_KEYDOWN()|Afx_msg "void" [OnKeyDown](../../mfc/reference/cwnd-class.md#onkeydown)("uint", "uint", "uint");|  
|ON_WM_KEYUP()|Afx_msg "void" [OnKeyUp](../../mfc/reference/cwnd-class.md#onkeyup)("uint", "uint", "uint");|  
|ON_WM_KILLFOCUS()|Afx_msg "void" [OnKillFocus](../../mfc/reference/cwnd-class.md#onkillfocus)(CWnd *);|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

