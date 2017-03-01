---
title: 'WM_-Meldungshandler: F - K | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- ON_WM_HELPINFO
- ON_WM_KILLFOCUS
- ON_WM_GETMINMAXINFO
- ON_WM_KEYUP
- ON_WM_HSCROLL
- ON_WM_INITMENUPOPUP
- ON_WM_FONTCHANGE
- ON_WM_ICONERASEBKGND
- ON_WM_GETDLGCODE
- ON_WM_HSCROLLCLIPBOARD
- ON_WM_INITMENU
- WM_ messages
- ON_WM_KEYDOWN
ms.assetid: 0e7de191-1499-499f-859c-62742797808e
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
ms.openlocfilehash: 7f803a7e73491abfabf9dba19288dcb44d1b68d7
ms.lasthandoff: 02/24/2017

---
# <a name="wm-message-handlers-f---k"></a>WM_-Meldungshandler: F - K
Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_FONTCHANGE()|Afx_msg Void [OnFontChange](../../mfc/reference/cwnd-class.md#onfontchange)();|  
|ON_WM_GETDLGCODE()|Afx_msg UINT [OnGetDlgCode](../../mfc/reference/cwnd-class.md#ongetdlgcode)();|  
|ON_WM_GETMINMAXINFO()|Afx_msg Void [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)(LPPOINT);|  
|ON_WM_HELPINFO()|Afx_msg BOOL [OnHelpInfo](../../mfc/reference/cwnd-class.md#onhelpinfo)(HELPINFO *);|  
|ON_WM_HOTKEY()|Afx_msg Void [OnHotKey](../../mfc/reference/cwnd-class.md#onhotkey)("uint", "uint", "uint");|  
|ON_WM_HSCROLL()|Afx_msg Void [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)(UINT, UINT, CWnd *);|  
|ON_WM_HSCROLLCLIPBOARD()|Afx_msg Void [OnHScrollClipboard](../../mfc/reference/cwnd-class.md#onhscrollclipboard)(CWnd *, "uint", "uint");|  
|ON_WM_ICONERASEBKGND()|Afx_msg Void [OnIconEraseBkgnd](../../mfc/reference/cwnd-class.md#oniconerasebkgnd)(CDC *);|  
|ON_WM_INITMENU()|Afx_msg Void [OnInitMenu](../../mfc/reference/cwnd-class.md#oninitmenu)(CMenu *);|  
|ON_WM_INITMENUPOPUP()|Afx_msg Void [OnInitMenuPopup](../../mfc/reference/cwnd-class.md#oninitmenupopup)(CMenu *, UINT, BOOL);|  
|ON_WM_INPUT()|Afx_msg Void [OnRawInput](../../mfc/reference/cwnd-class.md#onrawinput)(UINT, HRAWINPUT);|  
|ON_WM_INPUT_DEVICE_CHANGE()|Afx_msg Void [OnInputDeviceChange](../../mfc/reference/cwnd-class.md#oninputdevicechange)(kurz ohne Vorzeichen);|  
|ON_WM_INPUTLANGCHANGE()|Afx_msg Void [OnInputLangChange](../../mfc/reference/cwnd-class.md#oninputlangchange)(BYTE, UINT);|  
|ON_WM_INPUTLANGCHANGEREQUEST()|Afx_msg Void [OnInputLangChangeRequest](../../mfc/reference/cwnd-class.md#oninputlangchangerequest)(UINT, HKL);|  
|ON_WM_KEYDOWN()|Afx_msg Void [OnKeyDown](../../mfc/reference/cwnd-class.md#onkeydown)("uint", "uint", "uint");|  
|ON_WM_KEYUP()|Afx_msg Void [OnKeyUp](../../mfc/reference/cwnd-class.md#onkeyup)("uint", "uint", "uint");|  
|ON_WM_KILLFOCUS()|Afx_msg Void [OnKillFocus](../../mfc/reference/cwnd-class.md#onkillfocus)(CWnd *);|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)


