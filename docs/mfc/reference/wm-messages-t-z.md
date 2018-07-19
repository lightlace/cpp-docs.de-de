---
title: 'WM_-Meldungen: T - Z | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 517458158cd94421ba301047bcf3810f1cac3a08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379215"
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

