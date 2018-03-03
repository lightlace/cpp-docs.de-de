---
title: 'WM_-Meldungshandler: N - O | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 108afac12d47c009b423e62321eb31a78e2c09d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wm-message-handlers-n---o"></a>WM_-Meldungshandler: N - O
Die folgenden Zuordnungseinträge auf der linken Seite entsprechen auf der rechten Seite der Funktionsprototypen:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_NCACTIVATE()|Afx_msg BOOL [OnNcActivate](../../mfc/reference/cwnd-class.md#onncactivate)(BOOL);|  
|ON_WM_NCCALCSIZE()|Afx_msg "void" [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)(BOOL, NCCALCSIZE_PARAMS FAR *);|  
|ON_WM_NCCREATE()|Afx_msg BOOL [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)(LPCREATESTRUCT);|  
|ON_WM_NCDESTROY()|Afx_msg "void" [OnNcDestroy](../../mfc/reference/cwnd-class.md#onncdestroy)(;)|  
|ON_WM_NCHITTEST()|Afx_msg LRESULT [OnNcHitTest](../../mfc/reference/cwnd-class.md#onnchittest)(CPoint);|  
|ON_WM_NCLBUTTONDBLCLK()|Afx_msg "void" [OnNcLButtonDblClk](../../mfc/reference/cwnd-class.md#onnclbuttondblclk)("uint", CPoint);|  
|ON_WM_NCLBUTTONDOWN()|Afx_msg "void" [OnNcLButtonDown](../../mfc/reference/cwnd-class.md#onnclbuttondown)("uint", CPoint);|  
|ON_WM_NCLBUTTONUP()|Afx_msg "void" [OnNcLButtonUp](../../mfc/reference/cwnd-class.md#onnclbuttonup)("uint", CPoint);|  
|ON_WM_NCMBUTTONDBLCLK()|Afx_msg "void" [OnNcMButtonDblClk](../../mfc/reference/cwnd-class.md#onncmbuttondblclk)("uint", CPoint);|  
|ON_WM_NCMBUTTONDOWN()|Afx_msg "void" [OnNcMButtonDown](../../mfc/reference/cwnd-class.md#onncmbuttondown)("uint", CPoint);|  
|ON_WM_NCMBUTTONUP()|Afx_msg "void" [OnNcMButtonUp](../../mfc/reference/cwnd-class.md#onncmbuttonup)("uint", CPoint);|  
|ON_WM_NCMOUSEHOVER()|Afx_msg "void" [OnNcMouseHover](../../mfc/reference/cwnd-class.md#onncmousehover)("uint", CPoint);|  
|ON_WM_NCMOUSELEAVE()|Afx_msg "void" [OnNcMouseLeave](../../mfc/reference/cwnd-class.md#onncmouseleave)(;)|  
|ON_WM_NCMOUSEMOVE()|Afx_msg "void" [OnNcMouseMove](../../mfc/reference/cwnd-class.md#onncmousemove)("uint", CPoint);|  
|ON_WM_NCPAINT()|Afx_msg "void" [OnNcPaint](../../mfc/reference/cwnd-class.md#onncpaint)(;)|  
|ON_WM_NCRBUTTONDBLCLK()|Afx_msg "void" [OnNcRButtonDblClk](../../mfc/reference/cwnd-class.md#onncrbuttondblclk)("uint", CPoint);|  
|ON_WM_NCRBUTTONDOWN()|Afx_msg "void" [OnNcRButtonDown](../../mfc/reference/cwnd-class.md#onncrbuttondown)("uint", CPoint);|  
|ON_WM_NCRBUTTONUP()|Afx_msg "void" [OnNcRButtonUp](../../mfc/reference/cwnd-class.md#onncrbuttonup)("uint", CPoint);|  
|ON_WM_NCXBUTTONDBLCLK()|"void" [OnNcXButtonDblClk](../../mfc/reference/cwnd-class.md#onncxbuttondblclk)(kurzer Name, "uint", CPoint);|  
|ON_WM_NCXBUTTONDOWN()|Afx_msg "void" [OnNcXButtonDown](../../mfc/reference/cwnd-class.md#onncxbuttondown)(kurzer Name, "uint", CPoint);|  
|ON_WM_NCXBUTTONUP()|Afx_msg "void" [OnNcXButtonUp](../../mfc/reference/cwnd-class.md#onncxbuttonup)(kurzer Name, "uint", CPoint);|  
|ON_WM_NEXTMENU()|Afx_msg "void" [OnNextMenu](../../mfc/reference/cwnd-class.md#onnextmenu)("uint", LPMDINEXTMENU);|  
|ON_WM_NOTIFYFORMAT()|Afx_msg "uint" [OnNotifyFormat](../../mfc/reference/cwnd-class.md#onnotifyformat)(CWnd *, "uint");|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

