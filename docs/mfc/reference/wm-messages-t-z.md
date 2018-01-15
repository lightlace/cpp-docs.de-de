---
title: 'WM_-Meldungen: T - Z | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b71d7935b2064d5e83e5b6de5c0714b1db52b49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wm-messages-t---z"></a>WM_-Meldungen: T - Z
Die folgenden Zuordnungseinträge entsprechen der Funktionsprototypen:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_TCARD()|Afx_msg "void" [OnTCard](../../mfc/reference/cwnd-class.md#ontcard)("uint", DWORD);|  
|ON_WM_TIMECHANGE()|Afx_msg "void" [OnTimeChange](../../mfc/reference/cwnd-class.md#ontimechange)();|  
|ON_WM_TIMER()|Afx_msg "void" [bei Zeitgeber](../../mfc/reference/cwnd-class.md#ontimer)(UINT_PTR);|  
|ON_WM_UNICHAR()|Afx_msg "void" [OnUniChar](../../mfc/reference/cwnd-class.md#onunichar)("uint", "uint", "uint");|  
|ON_WM_UNINITMENUPOPUP()|Afx_msg "void" [OnUnInitMenuPopup](../../mfc/reference/cwnd-class.md#onuninitmenupopup)(CMenu *, "uint");|  
|ON_WM_USERCHANGED()|Afx_msg "void" [OnUserChanged](../../mfc/reference/cwnd-class.md#onuserchanged)(;)|  
|ON_WM_VKEYTOITEM()|Afx_msg Int [OnVKeyToItem](../../mfc/reference/cwnd-class.md#onvkeytoitem)("uint", CWnd *, "uint");|  
|ON_WM_VSCROLL()|Afx_msg "void" [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)("uint", "uint", CWnd *);|  
|ON_WM_VSCROLLCLIPBOARD()|Afx_msg "void" [OnVScrollClipboard](../../mfc/reference/cwnd-class.md#onvscrollclipboard)(CWnd *, "uint", "uint");|  
|ON_WM_WINDOWPOSCHANGED()|Afx_msg "void" [OnWindowPosChanged](../../mfc/reference/cwnd-class.md#onwindowposchanged)(WINDOWPOS *);|  
|ON_WM_WINDOWPOSCHANGING()|Afx_msg "void" [OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)(WINDOWPOS *);|  
|ON_WM_WININICHANGE()|Afx_msg "void" [OnWinIniChange](../../mfc/reference/cwnd-class.md#onwininichange)(LPSTR);|  
|ON_WM_WTSSESSION_CHANGE()|Afx_msg "void" [OnSessionChange](../../mfc/reference/cwnd-class.md#onsessionchange)("uint", "uint");|  
|ON_WM_XBUTTONDBLCLK()|Afx_msg "void" [OnXButtonDblClk](../../mfc/reference/cwnd-class.md#onxbuttondblclk)("uint", "uint", CPoint)|  
|ON_WM_XBUTTONDOWN()|Afx_msg "void" [OnXButtonDown](../../mfc/reference/cwnd-class.md#onxbuttondown)("uint", "uint", CPoint)|  
|ON_WM_XBUTTONUP()|Afx_msg "void" [OnXButtonUp](../../mfc/reference/cwnd-class.md#onxbuttonup)("uint", "uint", CPoint)|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

