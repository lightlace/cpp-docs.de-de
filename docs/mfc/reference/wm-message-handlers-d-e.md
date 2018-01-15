---
title: 'WM_-Meldungshandler: D - E | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
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
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68a11d88c4b6cb0c5235d54ac9d0333126f39765
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wm-message-handlers-d---e"></a>WM_-Meldungshandler: D - E
Die folgenden Zuordnungseinträge auf der linken Seite entsprechen auf der rechten Seite der Funktionsprototypen:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_DEADCHAR()|Afx_msg "void" [OnDeadChar](../../mfc/reference/cwnd-class.md#ondeadchar)("uint", "uint", "uint");|  
|ON_WM_DELETEITEM()|Afx_msg "void" [OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)(LPDELETEITEMSTRUCT);|  
|ON_WM_DESTROY()|Afx_msg "void" [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)(;)|  
|ON_WM_DESTROYCLIPBOARD()|Afx_msg "void" [OnDestroyClipboard](../../mfc/reference/cwnd-class.md#ondestroyclipboard)(;)|  
|ON_WM_DEVICECHANGE()|Afx_msg "void" [OnDeviceChange](../../mfc/reference/cwnd-class.md#ondevicechange)("uint", DWORD);|  
|ON_WM_DEVMODECHANGE()|Afx_msg "void" [OnDevModeChange](../../mfc/reference/cwnd-class.md#ondevmodechange)(LPSTR);|  
|ON_WM_DRAWCLIPBOARD()|Afx_msg "void" [OnDrawClipboard](../../mfc/reference/cwnd-class.md#ondrawclipboard)(;)|  
|ON_WM_DRAWITEM()|Afx_msg "void" [OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)(LPDRAWITEMSTRUCT);|  
|ON_WM_DROPFILES()|Afx_msg "void" [OnDropFiles](../../mfc/reference/cwnd-class.md#ondropfiles)(HDROP);|  
|ON_WM_DWMCOLORIZATIONCOLORCHANGED()|Afx_msg "void" [OnColorizationColorChanged](../../mfc/reference/cwnd-class.md#oncolorizationcolorchanged)(DWORD, BOOL);|  
|ON_WM_DWMCOMPOSITIONCHANGED()|Afx_msg "void" [OnCompositionChanged](../../mfc/reference/cwnd-class.md#oncompositionchanged)(;)|  
|ON_WM_DWMNCRENDERINGCHANGED()|Afx_msg "void" [OnNcRenderingChanged](../../mfc/reference/cwnd-class.md#onncrenderingchanged)(BOOL);|  
|ON_WM_DWMWINDOWMAXIMIZEDCHANGE()|Afx_msg "void" [OnWindowMaximizedChanged](../../mfc/reference/cwnd-class.md#onwindowmaximizedchanged)(BOOL);|  
|ON_WM_ENABLE()|Afx_msg "void" [OnEnable](../../mfc/reference/cwnd-class.md#onenable)(BOOL);|  
|ON_WM_ENDSESSION()|Afx_msg "void" [OnEndSession](../../mfc/reference/cwnd-class.md#onendsession)(BOOL);|  
|ON_WM_ENTERIDLE()|Afx_msg "void" [OnEnterIdle](../../mfc/reference/cwnd-class.md#onenteridle)("uint", CWnd *);|  
|ON_WM_ENTERSIZEMOVE()|Afx_msg "void" [OnEnterSizeMove](../../mfc/reference/cwnd-class.md#onentersizemove)(;)|  
|ON_WM_ERASEBKGND()|Afx_msg BOOL [OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd)(CDC *);|  
|ON_WM_EXITSIZEMOVE()|Afx_msg "void" [OnExitSizeMove](../../mfc/reference/cwnd-class.md#onexitsizemove)(;)|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

