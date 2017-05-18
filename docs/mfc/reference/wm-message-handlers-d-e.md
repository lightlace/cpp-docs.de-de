---
title: 'WM_-Meldungshandler: D - E | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_ENTERIDLE
- ON_WM_DESTROYCLIPBOARD
- ON_WM_DEADCHAR
- ON_WM_DEVMODECHANGE
- ON_WM_ERASEBKGND
- ON_WM_DESTROY
- ON_WM_DRAWCLIPBOARD
- ON_WM_ENDSESSION
- ON_WM_DRAWITEM
- ON_WM_ENABLE
- ON_WM_DROPFILES
- ON_WM_DELETEITEM
- ON_WM_DEVICECHANGE
- WM_ messages
ms.assetid: 56fb89c8-68a8-4adf-883e-a9f63bf677e9
caps.latest.revision: 16
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
ms.openlocfilehash: 0dbd7e3649cddd353077b8364482ad98d55283a1
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="wm-message-handlers-d---e"></a>WM_-Meldungshandler: D - E
Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_DEADCHAR()|Afx_msg Void [OnDeadChar](../../mfc/reference/cwnd-class.md#ondeadchar)("uint", "uint", "uint");|  
|ON_WM_DELETEITEM()|Afx_msg Void [OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)(LPDELETEITEMSTRUCT);|  
|ON_WM_DESTROY()|Afx_msg Void [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)();|  
|ON_WM_DESTROYCLIPBOARD()|Afx_msg Void [OnDestroyClipboard](../../mfc/reference/cwnd-class.md#ondestroyclipboard)();|  
|ON_WM_DEVICECHANGE()|Afx_msg Void [OnDeviceChange](../../mfc/reference/cwnd-class.md#ondevicechange)(UINT, DWORD);|  
|ON_WM_DEVMODECHANGE()|Afx_msg Void [OnDevModeChange](../../mfc/reference/cwnd-class.md#ondevmodechange)(LPSTR);|  
|ON_WM_DRAWCLIPBOARD()|Afx_msg Void [OnDrawClipboard](../../mfc/reference/cwnd-class.md#ondrawclipboard)();|  
|ON_WM_DRAWITEM()|Afx_msg Void [OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)(LPDRAWITEMSTRUCT);|  
|ON_WM_DROPFILES()|Afx_msg Void [OnDropFiles](../../mfc/reference/cwnd-class.md#ondropfiles)(HDROP);|  
|ON_WM_DWMCOLORIZATIONCOLORCHANGED()|Afx_msg Void [OnColorizationColorChanged](../../mfc/reference/cwnd-class.md#oncolorizationcolorchanged)(DWORD, BOOL);|  
|ON_WM_DWMCOMPOSITIONCHANGED()|Afx_msg Void [OnCompositionChanged](../../mfc/reference/cwnd-class.md#oncompositionchanged)();|  
|ON_WM_DWMNCRENDERINGCHANGED()|Afx_msg Void [OnNcRenderingChanged](../../mfc/reference/cwnd-class.md#onncrenderingchanged)(BOOL);|  
|ON_WM_DWMWINDOWMAXIMIZEDCHANGE()|Afx_msg Void [OnWindowMaximizedChanged](../../mfc/reference/cwnd-class.md#onwindowmaximizedchanged)(BOOL);|  
|ON_WM_ENABLE()|Afx_msg Void [OnEnable](../../mfc/reference/cwnd-class.md#onenable)(BOOL);|  
|ON_WM_ENDSESSION()|Afx_msg Void [OnEndSession](../../mfc/reference/cwnd-class.md#onendsession)(BOOL);|  
|ON_WM_ENTERIDLE()|Afx_msg Void [OnEnterIdle](../../mfc/reference/cwnd-class.md#onenteridle)(UINT, CWnd *);|  
|ON_WM_ENTERSIZEMOVE()|Afx_msg Void [OnEnterSizeMove](../../mfc/reference/cwnd-class.md#onentersizemove)();|  
|ON_WM_ERASEBKGND()|Afx_msg BOOL [OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd)(CDC *);|  
|ON_WM_EXITSIZEMOVE()|Afx_msg Void [OnExitSizeMove](../../mfc/reference/cwnd-class.md#onexitsizemove)();|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)


