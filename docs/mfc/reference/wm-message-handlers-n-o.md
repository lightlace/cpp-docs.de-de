---
title: 'WM_-Meldungshandler: N - O | Microsoft-Dokumentation'
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
- ON_WM_NCCALCSIZE
- ON_WM_NCMBUTTONDOWN
- ON_WM_NCRBUTTONDBLCLK
- ON_WM_NCMBUTTONDBLCLK
- ON_WM_NCLBUTTONDBLCLK
- ON_WM_NCDESTROY
- ON_WM_NCRBUTTONDOWN
- ON_WM_NCLBUTTONDOWN
- ON_WM_NCCREATE
- ON_WM_NCRBUTTONUP
- ON_WM_NCLBUTTONUP
- ON_WM_NCPAINT
- ON_WM_NCACTIVATE
- ON_WM_NCHITTEST
- ON_WM_NCMOUSEMOVE
- ON_WM_NCMBUTTONUP
- WM_ messages
ms.assetid: 4efd1cda-b642-4e8b-89e8-73255fa70d77
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f1e2a3a42c105e5f0e6d0fca714c5cd4d1216f2f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="wm-message-handlers-n---o"></a>WM_-Meldungshandler: N - O
Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_NCACTIVATE()|Afx_msg BOOL [OnNcActivate](../../mfc/reference/cwnd-class.md#onncactivate)(BOOL);|  
|ON_WM_NCCALCSIZE()|Afx_msg Void [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)(BOOL, NCCALCSIZE_PARAMS FAR *);|  
|ON_WM_NCCREATE()|Afx_msg BOOL [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)(LPCREATESTRUCT);|  
|ON_WM_NCDESTROY()|Afx_msg Void [OnNcDestroy](../../mfc/reference/cwnd-class.md#onncdestroy)();|  
|ON_WM_NCHITTEST()|Afx_msg LRESULT [OnNcHitTest](../../mfc/reference/cwnd-class.md#onnchittest)(CPoint);|  
|ON_WM_NCLBUTTONDBLCLK()|Afx_msg Void [OnNcLButtonDblClk](../../mfc/reference/cwnd-class.md#onnclbuttondblclk)(UINT, CPoint);|  
|ON_WM_NCLBUTTONDOWN()|Afx_msg Void [OnNcLButtonDown](../../mfc/reference/cwnd-class.md#onnclbuttondown)(UINT, CPoint);|  
|ON_WM_NCLBUTTONUP()|Afx_msg Void [OnNcLButtonUp](../../mfc/reference/cwnd-class.md#onnclbuttonup)(UINT, CPoint);|  
|ON_WM_NCMBUTTONDBLCLK()|Afx_msg Void [OnNcMButtonDblClk](../../mfc/reference/cwnd-class.md#onncmbuttondblclk)(UINT, CPoint);|  
|ON_WM_NCMBUTTONDOWN()|Afx_msg Void [OnNcMButtonDown](../../mfc/reference/cwnd-class.md#onncmbuttondown)(UINT, CPoint);|  
|ON_WM_NCMBUTTONUP()|Afx_msg Void [OnNcMButtonUp](../../mfc/reference/cwnd-class.md#onncmbuttonup)(UINT, CPoint);|  
|ON_WM_NCMOUSEHOVER()|Afx_msg Void [OnNcMouseHover](../../mfc/reference/cwnd-class.md#onncmousehover)(UINT, CPoint);|  
|ON_WM_NCMOUSELEAVE()|Afx_msg Void [OnNcMouseLeave](../../mfc/reference/cwnd-class.md#onncmouseleave)();|  
|ON_WM_NCMOUSEMOVE()|Afx_msg Void [OnNcMouseMove](../../mfc/reference/cwnd-class.md#onncmousemove)(UINT, CPoint);|  
|ON_WM_NCPAINT()|Afx_msg Void [OnNcPaint](../../mfc/reference/cwnd-class.md#onncpaint)();|  
|ON_WM_NCRBUTTONDBLCLK()|Afx_msg Void [OnNcRButtonDblClk](../../mfc/reference/cwnd-class.md#onncrbuttondblclk)(UINT, CPoint);|  
|ON_WM_NCRBUTTONDOWN()|Afx_msg Void [OnNcRButtonDown](../../mfc/reference/cwnd-class.md#onncrbuttondown)(UINT, CPoint);|  
|ON_WM_NCRBUTTONUP()|Afx_msg Void [OnNcRButtonUp](../../mfc/reference/cwnd-class.md#onncrbuttonup)(UINT, CPoint);|  
|ON_WM_NCXBUTTONDBLCLK()|void [OnNcXButtonDblClk](../../mfc/reference/cwnd-class.md#onncxbuttondblclk)(kurz, UINT, CPoint);|  
|ON_WM_NCXBUTTONDOWN()|Afx_msg Void [OnNcXButtonDown](../../mfc/reference/cwnd-class.md#onncxbuttondown)(kurz, UINT, CPoint);|  
|ON_WM_NCXBUTTONUP()|Afx_msg Void [OnNcXButtonUp](../../mfc/reference/cwnd-class.md#onncxbuttonup)(kurz, UINT, CPoint);|  
|ON_WM_NEXTMENU()|Afx_msg Void [OnNextMenu](../../mfc/reference/cwnd-class.md#onnextmenu)(UINT, LPMDINEXTMENU);|  
|ON_WM_NOTIFYFORMAT()|Afx_msg UINT [OnNotifyFormat](../../mfc/reference/cwnd-class.md#onnotifyformat)(CWnd *, "uint");|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)


